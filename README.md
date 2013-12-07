# kml2xmp

Attach location history recorded in kml to RAW photos as .xmp sidecar files

## Usage

    kml2gmp location-history.kml ~/Photos

## How it works

Decodes kml for track info, and then locate the position for each photo taken, and creates .xml sidecar files next to the raw file, when it doesn't exist already.

kml2xmp uses `sips` command (comes with Mac OS X) to get the creation date of your photo. The program assumes the date is local time and your computer's timezone matches with it. If you are going to sync photos taken in a different timezone, try running the script with `TZ` environment variable set to the Olson DB equivalent, such as `America/Los_Angeles` or `Asia/Tokyo`.

## Why

I geotag photos with [Eye-Fi](http://www.eye.fi) and [gps4cam](http://gps4cam.com/). Eye-Fi often doesn't recognize Wi-Fi locations, and gps4cam drains battery (or simply I forget to run it).

kml2xmp allows you to download your KML history from [Google Location History](https://maps.google.com/locationhistory/b/0) and geotag photos with `.xmp` sidecar files. Google Location History is updated by your phone already if you use Google Now, and is more available than Wi-Fi, if not accurate.

I'm sure there are tools like gpsbabel and bunch of GPX geotagging tools that does it, but I thought writing it myself is easier (and fun).

## Author

Tatsuhiko Miyagawa
