# website pmii radar

## konfigurasi website deploy pada netlify

[build]
  publish = "exampleSite/public"
  command = "hugo --gc --minify"
  
[build.environment]
  HUGO_VERSION = "0.89.4"
  HUGO_BASEURL = "https://pmiiradar.org"

[[headers]]
  # Define which paths this specific [[headers]] block will cover.
  for = "/*"

  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    Content-Security-Policy = "default-src https: 'unsafe-eval' 'unsafe-inline'; object-src 'none'"
    Strict-Transport-Security = "max-age=63072000; includeSubDomains; preload"
    Referrer-Policy = "no-referrer-when-downgrade"
    X-Content-Type-Options = "nosniff"
    Permissions-Policy = '''
            accelerometer=(none),
            ambient-light-sensor=(none),
            autoplay=(none),
            camera=(none),
            encrypted-media=(none),
            fullscreen=(none),
            geolocation=(none),
            gyroscope=(none),
            magnetometer=(none),
            microphone=(none),
            midi=(none),
            payment=(none),
            picture-in-picture=(none),
            speaker=(none),
            usb=(none),
            vibrate=(none),
            vr=(none)
        '''
