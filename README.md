SEVERN EYE

Passive RF monitoring station covering ADS-B (aviation) and AIS (maritime) traffic over the Bristol Channel.

What it is

The idea is to track two totally different signal types over the same bit of coastline: aircraft transponders (ADS-B) and ship tracking beacons (AIS), and run them through the same anomaly detection pipeline instead of treating them as separate problems. Nobody really looks at aviation and maritime traffic together, so that's the angle.

Status (being honest here)
AIS anomaly detection: built and working. Runs unsupervised anomaly detection on vessel tracking data to catch dodgy position/speed/course reports.
Live dual RTL-SDR receiver station: designed but not built yet. Waiting on a second SDR unit before I can get this properly off the ground.
Public dashboard: on the list, not started.

Basically this repo is the AIS software for now. Built it to work standalone off public feed data so it doesn't need the hardware finished to be useful.

Why bother doing both

Both ADS-B and AIS broadcast unencrypted position data that can be spoofed or messed with. The kind of weird patterns you're looking for (impossible speed jumps, positions that don't make physical sense) show up in both, even though nobody treats them as the same problem. Building one detection approach that works for both felt like the more interesting version of this project.

Tech stack

Python, RTL-SDR, dump1090 (once the hardware's in), scikit-learn (Isolation Forest, same approach as SKYPOINTER), AIS decoding

What's next
Finish documenting the AIS pipeline properly
Get a second RTL-SDR so I can actually run ADS-B and AIS at the same time
Get the receiver station physically set up over the Bristol Channel
Build the dashboard so it's not just something on my laptop
About me

Luke, CS student at Swansea, into ML for cybersecurity and defence stuff. github.com/Brucee-ee
