# HackRF



To install Software used to Spoof GPS:

- https://hackrf.readthedocs.io/en/latest/hackrf_tools.html

Hardware required:

- https://lab401.com/es-es/products/hackrf-one

The daily GPS broadcast ephemeris file (brdc):

- https://cddis.nasa.gov/archive/gnss/data/daily/

Tutorial:

- https://www.youtube.com/watch?v=3NWn5cQM7q4

References used:

- https://www.rtl-sdr.com/using-a-hackrf-for-gps-spoofing-on-windows/
- https://greatscottgadgets.com/hackrf/
- https://github.com/greatscottgadgets/hackrf
- https://github.com/osqzss/gps-sdr-sim

How to do:

1º) Compile gpssim.c

> gcc gpssim.c -lm -O3 -o gps-sdr-sim -DUSER_MOTION_SIZE=4000

2º) Generate .bin with coordenades

> gps-sdr-sim -e brdc0140.25n -b 8 -l 25.761975,-80.193620,100

3º) Spoof GPS!!

> hackrf_transfer -t gpssim.bin -f 1575420000 -s 2600000 -a 1 -x 0

