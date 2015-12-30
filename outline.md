# SDR talk

## Topics to cover:

- Radio basics
  - electromagnetic waves
  - define terms:
    - amplitude
    - frequency
    - phase
  - basic modulations:
    - Analog modulations (continuous values)
      - frequency modulation
      - amplitude modulation
  - Relationship between trigonometric and complex exponential
  - Fourier transform
    - Define: takes infinitely repeating, continuous time signal, breaks it down into frequency components
    - Examples: sine wave, square wave, triangle wave
      - demonstrate how square wave can be constructed of many sine waves
    - Reversible: inverse fourier transform
    - DFT: FT can be done in discrete time, on time-limited sections
      - spectrum analyzers (image: periodogram)
      - waterfall chart / spectrogram (image: spectrogram, inspectrum, baudline)
  - Let's look at our modulations in the frequency domain
    - FM
      - oh hey it's a wavy line
      - kinda looks like our audio.
      - pretty much what you'd expect.
      - let's zoom out (take longer FFTs) and explore relationship of audio bandwidth to radio bandwidth
    - AM
      - show spectrogram of AM signal
      - what's going on with those side bands?
        - show math that explains those, using complex exponentials (TODO: math)
    - SSB: a modification of AM
      - In AM, the carrier contains no/little information
      - Also, the upper and lower side bands
      - we're wasting >half of our power on redundant frequencies
      - Let's just go ahead and cut these out using a high pass filter.
  - Heterodyne / frequency shifting
    - Multiplying two signals produces side bands at the sum and difference of the two frequencies
    - What if we took an RF signal (from an antenna, perhaps), amplitude modulated it with some nearby frequency?
    - We'd end up with the original signal, frequency shifted down.
    - If you shift all the way down to zero, you can demodulate SSB
    - However, there's a problem: any signal just below your local oscillator frequency also gets shifted down.
    - The problem is that we can't distinguish negative frequencies from positive frequencies. How do we do that?