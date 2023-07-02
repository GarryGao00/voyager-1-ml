
                                  Bundle 

                                 Voyager 1

                     Plasma Wave Spectrometer Waveform

                              PDS Data Archive

                                Entire Mission

                Planetary Plasma Interactions Discipline Node

                                   of the

                            Planetary Data System


This bundle contains the Voyager 1 Plasma Wave Spectrometer Waveform data from
spacecraft event times 1978-08-21 to 2022-10-26, submitted to the Planetary
Data System (PDS).   Every effort has been made to assure that the data and
documentation are of the best possible quality.  However, mistakes are
inevitable.  The PPI Node of the PDS will maintain an online list of ERRATA
where errors and updates are documented.  Should any user of this product find
an error on this bundle, please report the error to the PPI Node so that the
finding can be made public.  All users are encouraged to verify the
"correctness" of the data prior to submitting any publications or other work
based on these data.  Users of these data are encouraged to acknowledge both
the PDS and the principal investigators of the instruments whose data is used
in analysis in all publications.



==============================================================================
Dataset Description
==============================================================================

Contents
--------
The Voyager 1 Plasma Wave Spectrometer (PWS) raw full resolution data set
includes all electric field waveform data for the entire Voyager 1 mission.


Abstract
--------
The Voyager 1 Plasma Wave Spectrometer (PWS) raw full resolution waveform data
set consists of electric field waveform samples from the Voyager 1 Plasma Wave
Science waveform receiver obtained during the entire mission.  Data will
continue to be added to the archive via updates to this bundle.  The data set
encompasses all waveform observations obtained in the cruise mission phases
before, between, and after the Jupiter and Saturn encounter phases as well as
those obtained during the two encounter phases.  Data for this data set are
acquired from the PWS waveform receiver.  Data are presented as time series of
4-bit voltage measurements acquired at the rate of 28,800 samples per second
through a 40 Hz to 12 kHz bandpass filter.  An automatic gain control is used
to keep the signal within the usable range of the 4-bit digitization, however,
the gain information is not returned to the ground, hence, there is no direct,
absolute calibration.  However, a power spectrum analysis returns a spectrum
that has accurate relative amplitudes between spectral elements.  This data
set provides the highest temporal resolution data from the Voyager mission.


Citation
--------
Kurth, W.S., and C.W. Piker, Voyager 1 Plasma Wave Spectrometer Raw Waveform
60ms V1.0, NASA Planetary Data System, 2022.


Overview
--------
This data set consists of electric field waveform samples from the Voyager 1
Plasma Wave Subsystem waveform receiver obtained during the entire mission.
Data after 2022-10-26 will be added to the archive in subsequent
releases.  The data set encompasses all waveform observations obtained in the
cruise mission phases before, between, and after the Jupiter and Saturn
encounter phases as well as those obtained during the two encounter phases.

The Voyager 1 spacecraft travels from Earth to well beyond 100 AU over the
course of this data set.  To provide some guidance on when some key events
occurred during the mission, the following table is provided.

   Date         Event
   ----------   -------------------------------------------------
   1977-09-05   Launch
   1979-02-28   First inbound bow shock crossing at Jupiter
   1979-03-22   Last outbound bow shock crossing at Jupiter
   1980-11-11   First inbound bow shock crossing at Saturn
   1980-11-16   Last outbound bow shock crossing at Saturn
   1981-02-20   10 AU
   1983-08-30   Onset of first major LF heliospheric radio event
   1984-06-19   20 AU
   1987-04-08   30 AU
   1990-01-09   40 AU
   1992-07-06   Onset of second major LF heliospheric radio event
   1992-10-10   50 AU
   1995-07-14   60 AU
   1998-04-18   70 AU
   2001-01-25   80 AU
   2002-11-01   Onset of third major LF heliospheric radio event
   2003-11-05   90 AU
   2004-12-16   Termination shock crossing
   2006-08-16   100 AU
   2009-05-31   110 AU
   2012-03-16   120 AU
   2012-08-25   121 AU Heliopause crossing
   2015-01-01   130 AU
   2017-10-20   140 AU
   2020-08-09   150 AU
   2023-05-31   160 AU
   2026-03-23   170 AU
   2029-01-12   180 AU


Sampling
--------
The waveform is sampled at 4-bit resolution through a bandpass filter with a
passband of 40 Hz to 12 kHz.  1600 samples are collected in 55.56 msec (at a
rate of 28,800 samples per second) followed by a 4.44-msec gap.  Each 60-msec
interval constitutes a line of waveform samples.  The data set includes frames
of waveform samples consisting of up to 800 lines, or 48 seconds, each.  The
telemetry format for the waveform data is identical to that for images, hence
the use of line and frame as constructs in describing the form of the data.  
For data acquired after the Jupiter flyby, these data are recorded on the
digital tape recorder (DTR).  After 1993, only every fifth line is returned 
in telemetry.  The reason for this is that the maximum downlink rate supported 
by the Voyager-to-DSN link is 1.4 kbps while the minimum playback rate of the 
DTR is 7.2 kbps.  Hence, as one line is telemetered to the ground, the
following four are lost.  Clearly, this results in a decrease in temporal
resolution to 300 ms between lines and a resulting decrease in signal to noise
ratio that might be achieved by averaging spectra across the 48-seconds
spanned by the frame.


Processing
----------
Because there is no direct method for calibrating these data and because a
single byte per measurement is a convenient storage format, these data are
stored as small integers. The raw ADC values (0 to 15) have been scaled using:

  RAW * 2 - 15
  
and thus all data values are in the set:

  (-15, -13, -11, -9, -7, -5, -3, -1, 1, 3, 5, 7, 9, 11, 13, 15)

Since the instrument was tuned to produce raw values of either 7 or 8 on even
a slight departure from a null voltage differential, 0 on this scale 
represents a null measurement, even though zeros are not present in the
product files due to the quantizing effects of analog to digital conversion.

The data may be plotted directly to show the actual waveform; this is useful
for studying events such as dust impacts on the spacecraft.  But the normal
method of analyzing the waveform data is by Fourier transforming the samples
from each line to arrive at an amplitude versus frequency spectrum.  By 
stacking the spectra side-by-side in time order, a frequency-time spectrogram
can be produced.


Dynamic Range and Calibration
-----------------------------
The waveforms are collections of samples of the electric field measured by the
dipole electric antenna and the 4-bit samples provide sixteen digital values
of the electric field with a linear amplitude scale, but the amplitude scale
is arbitrary because of the automatic gain control used in the waveform
receiver.  The instantaneous dynamic range afforded by the 4 bit samples is
about 23 dB, but the automatic gain control allows the dominant signal in the
passband to be set at the optimum level to fit within the instantaneous
dynamic range.  With the gain control, the overall dynamic range of the
waveform receiver is about 100 dB.  The automatic gain control gain setting
is not returned to the ground, hence, there is no absolute calibration for the
data.  However, by comparing the waveform spectrum derived by Fourier
transforming the waveform to the spectrum provided by the spectrum analyzer
data, an absolute calibration may be obtained in most cases.


Interference
------------
There has been no attempt to clean various interference signals from the data.
Most of these can normally be easily seen in frequency-time spectrograms as
narrowband, fixed-frequency tones.  The most common include narrow-band tones
at 2.4 and 4.8 kHz which are power supply harmonics.  There is sometimes a tone
near 1.7 kHz which is associated with the operation of the spacecraft gyros.  
The spacecraft tape recorder results in a rather intense band in the frequency
range of a few hundred Hertz.  There are few times when the data in this
frequency range can be used.  However, there are times when the real signals in
this frequency range can exceed the intensity of the interference sufficiently
so that the frequency range near a few hundred Hz can be used.  Use of the
spectrum analyzer data can be of use to determine when these time periods
occur.  The stepper motor of the LECP instrument also interferes in the 
frequency range of a few hundred Hz, but for periods of a few seconds.  The
LECP interference is very intense and captures the automatic gain control so
that real signals, even where there is no interference, will appear to decrease
in amplitude until the LECP interference fades in amplitude.  The PLS 
instrument periodically interferes at 400 Hz and odd harmonics because of a
400-Hz square wave used to modulate a grid in the detector.  The PLS
interference lasts for several seconds and ends abruptly.

Telemetry errors result in a fairly graceful degradation of the waveform data.
Assuming the telemetry errors are randomly occurring bursts, they typically
appear as an enhanced background level in the spectrum.  Since the bursts are
short, their Fourier transform is a broadband spectrum.  When looking for
relatively narrowband features or features with distinct frequency-time
characteristics, the result of the bursts simply reduce the signal-to-noise in
the spectrum.  One way of reducing the effect of burst telemetry errors is to
pass the waveform data through a low-pass filter to despike it, prior to
running the Fourier transform.


Coordinates
-----------
The electric dipole antenna detects electric fields in a dipole pattern with
peak sensitivity parallel to the spacecraft x-axis.  However, no attempt has
been made to correlate the measured field to any particular direction such as
the local magnetic field or direction to a planet.  This is because the
spacecraft remains in a 3-axis stabilized orientation almost continuously,
and these data are not obtained during the infrequent calibration turns.
Furthermore, the automatic gain control feature would tend to counteract any
orientation-dependent amplitude variations.



==============================================================================
Bundle Description
==============================================================================

Key things to know when using this bundle:

* Specific information about a data file *.cdf is found in the same directory
  in the label file *.xml.
    
* Data files are in uncompressed CDF (Common Data Format) and follow ISTP
  (International Solar-Terrestrial Physics) metadata guidelines for each
  record, though there is a second time field for the offsets between waveform
  samples in a record.
        
* All files are stored in the "data" directory tree by hourly SCET (SpaceCraft
  Event Time) coverage periods.  Thus, for example, all data for SCET hour
  2020-03-16T21:00 to 2020-03-16T22:00 are in a the product file
  "vg1_pws_wf_2020-03-16T21_v0.9.xml"

* Voyager PWS waveform data are sparse, especially during interplanetary and
  interstellar cruise.  Most hourly files in these regions will only have
  around a minute or two of regularly sampled field values.  This is normal.
  On the other hand, near planetary encounters PWS was operated with a much
  higher duty cycle.
  
* As detailed above, Voyager PWS waveforms are scaled using an onboard AGC
  and the AGC states are not transmitted to the ground.  These data are 
  uncalibrated.
  
* Apart from this file, most of the relevant information about the Voyager
  mission and the PWS instrument are contained in PDS "Context Collections"
  and are only referenced here by their PDS logical identification (LID).


Relationship to Other Bundles
-----------------------------
The data on this disk are Voyager Plasma Wave Spectrometer Waveform Data which
are the highest resolution wave information available from the Voyager Plasma
Wave Receiver.  Since they require very high data rates these data are only
available for short periods of time with a low duty cycle.  Low resolution
spectrum analyzer data which are available for all times during which the
Plasma Wave Receiver is on and telemetry is available are found in the 
bundles:

  urn:nasa:pds:voyager1.pws.sa
  urn:nasa:pds:voyager2.pws.sa

which are available elsewhere within the Planetary Data System.

An older version of this data set resides in the PDS, archived under PDS3
standards:

VG1-J/S/SS-PWS-1-EDR-WFRM-60MS-V1.0
https://doi.org/10.17189/1519903

Software
--------
Many common CDF aware tools may be used to read the data product files.  Even
though the PDS labels are the authoritative source of metadata about each
product, the product files also contain full ISTP metadata for use by non PDS4
applications.


Contents and Structure
----------------------
Below is a tree diagram of the volume, followed by a description of the
directory function and key files in each directory.

  [voyager1-pws-wf]       Root directory
   |
   |- [data]              Contains the data collection definition as well as
   |                      yearly subdirectories of data product files.
   |
   |- [index]             Contains an index of PDS label files for all data
   |                      archived on this volume and on the volume set to
   |                      date.
   |
   |- bundle.xml          A PDS structure defining the bundle.
   |
   |- readme.txt         Describes bundle contents, organization, and use
                          (this file).
   
Contacts
--------
The person most directly responsible for the release of this bundle is Joe
Mafi.  He was the PPI Node Data Administrator at the time this bundle was 
drafted as much about the structure and data organization as anyone.  Other 
PPI personnel who may be aware of issues related to this volume include Dr.
William Kurth and Dr. Raymond Walker, the PDS/PPI Node manager.

For questions or problems regarding this volume, please contact the PDS/PPI
PDS operator:

     Internet   pds_operator@igpp.ucla.edu
     Telephone  (310) 206-6073
                PDS Operator
                c/o Dr. Raymond Walker

For questions regarding PDS Standards or other volumes available from the PDS,
please contact PDS Operator at the PDS Central Node (at JPL):

     Internet   pds_operator@jpl.nasa.gov
     Telephone  (818) 354-4321
                Planetary Data System, PDS Operator
                Jet Propulsion Laboratory


Disclaimer
----------
The PDS and the Planetary Plasma Interactions (PPI) Node in particular, assume
no legal liability for errors on this disk.  All users are encouraged to
verify the "correctness" of the data prior to submitting any publications or
other work based on these data.  Errors on this disk should be reported back
to the PPI Node of the PDS via the contacts above.

All trademarks are acknowledged as the property of their respective owners. 
The producers and publishers of this archive do not endorse any commercial
entities which may be mentioned for clarity.



==============================================================================
Acknowledgments
==============================================================================

These data were collected under the auspices of the Voyager Project.  
Fred Scarf, Donald A. Gurnett, and William Kurth have been the Plasma Wave 
Spectrometer Principal Investigators.
The archiving effort at The University of Iowa was coordinated by W. Kurth 
and supported by C. Piker and L. Granroth.

This archiving effort was supported by the Planetary Plasma Interactions Node
of the Planetary Data System.  Assistance was provided by J. Mafi and 
D. Kazden of the University of California, Los Angeles.

