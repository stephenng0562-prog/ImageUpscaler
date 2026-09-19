# Privacy

**Short version: this app collects nothing, sends nothing, and needs no
account. Your photos never leave your computer.**

That is the reason it exists. The usual way to enlarge a photo is to upload it
to a website, which hands your picture to someone else's server where it may be
stored, cached or used in ways you never see. This app does the same job on your
own machine instead.

## What the app does with your photos

* Reads the image file you choose.
* Processes it entirely on your own hardware — your graphics card for enlarging,
  your processor for face restoration.
* Writes the result where you tell it to.

While a job is running, one working copy is written to your system temporary
folder (`%TEMP%\image_upscaler_ui\<session>`) so that Save has something to copy
from. That folder is cleared when you close the window, and any copies left
behind by an earlier session are swept on the next launch.

## The one server it runs

The interface is a local web page rendered inside the app's own window, so the
app runs **a small web server on 127.0.0.1** whose only job is to hand that page
and its stylesheet to the window.

Being precise about what that does and does not mean:

* `127.0.0.1` is your own machine. Nothing outside it can reach that server.
* It serves the app's own interface files and nothing else. **No photograph ever
  passes through it** — images reach the page as data the app hands over
  directly, in memory.
* It is started by the window and dies with it. It listens on a random free port
  and is never advertised anywhere.

It is set out here because "this app does no networking at all" would be the
tidier sentence, and it would not be strictly true. A loopback server is still a
server, and you should hear about it from us rather than find it yourself.

## What the app does not do

* **No uploading.** There is nothing in it that can transmit an image anywhere.
* **No telemetry or analytics.** No usage statistics, no crash reporting, no
  "anonymous diagnostics".
* **No accounts, licence keys or activation.**
* **No update checks.** It never phones home to see if a new version exists.
* **No advertising or tracking of any kind.**

## The only times anything reaches the internet

1. **First-time setup, when running from source.** The engine download script
   fetches the AI models from GitHub and Hugging Face. That downloads *to* you
   and uploads nothing. The packaged Windows release already contains the models
   and never does this.
2. **Clicking a credit link on the About page**, which opens that address in your
   normal web browser.

Neither ever involves your photos.

## Photographs of other people

Portrait mode is designed for photos of people, and those are personal data in
the ordinary sense. Because everything stays on your device, no one else — the
authors of this app included — ever receives them, and there is no server where
they could be retained. Whatever obligations you have towards the people in your
photos are unaffected by this app; it simply never becomes a third party to them.

## Verifying this yourself

You do not have to take any of it on trust. The source is public, and the claim
above is a structural one you can check in a few seconds. Search the app's own
code for anything capable of sending a file somewhere:

```bash
grep -rE "^\s*(import|from)\s+(urllib|requests|httpx|aiohttp|socket|ftplib|smtplib)" shell/ app/
```

That returns nothing. The loopback server is `bottle`, started by `pywebview`,
and it is the only socket in the process. The only external programs the app ever
launches are the bundled Real-ESRGAN engine, Windows Explorer when you click
"Show in folder", and your image viewer when you click "Open full size".

## Contact

Please open an issue on the project's repository.
