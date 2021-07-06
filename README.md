# Introduction-to-Fast-Fourier-Transform
Suppose you have an audio file, or even a video file, or let's say you have an image file. But the only problem is it has lots of noise. You can't distinguish between the required audio, frames, or the object in the three files respectively. So how are you supposed to distinguish between the noise and the actual signal?.

The odds are quite high that the file may contain a term called noise. Though the terms are of the communication domain, they are also involved in the AI domain.
<h3> Noise </h3>
Noise is a random signal which consists of equal intensities or powers at every frequency. In computing, it is statistically defined as a sequence of random variables. So basically, in very simple terms, it is a random thing that may be a part of your signal.
<h3>But is Noise an unwanted signal?</h3>
The answer is Yes and No. I will tell you why. Like I mentioned in the scenario above, if you have one or all three files (audio, video, and image), they may contain noise or unwanted signals (in audio), or a spectrum of wavelengths (in frames or images). Here the noise will be defined as unwanted because if you have a music file and there is a random muting, distortion of the sound, you certainly don't want that.

Now white noise can also be a wanted noise. In deep learning, noise can be intentionally fed to a neural network to improve its performance. In the previous article, Understanding of Regularization in Neural Networks, we talked about how the dropout method drops some neurons or zeroes them out. This is nothing but a form of adding noise to those neurons. Furthermore, in Generative Adversarial Networks (GAN), you feed random noise so that the discriminator can train the GAN.

Let's talk about the noise as an unwanted signal and how can we remove it.
<h3>Fourier Transformation (FT)</h3>
Fourier Transformation which is the main highlight of this article is a very useful tool for analyzing signals, especially noisy signals. It transforms or converts complex mathematical equations into simpler trigonometric functions in terms of sin or cos. Sin or Cos are used because the signal is easier to analyze in their format. In other terms, Fourier transformation is used to convert time signals into frequency signals and power signals. You are using the applications of Fourier Transformation unknowingly every day.
<h3>Why do we need to use Fourier Transformation?</h3>
Let's define some terms first

<h4>Frequency</h4>

It is defined as the speed or rate at which an entity changes. In the case of a signal, frequency is the rate at which the intensity/power of the signal changes. It is defined as samples/sec and the unit is Hertz (Hz).
<h4>Periodic Function</h4>

It is a type of function where the function retains its value after regular intervals. For example, a sine function.
<h4>Non-Periodic Function</h4>

It is a type of function where the function does not retain its value after regular intervals or multiples of the integer values. For example, an exponential function.
Let's just start with this. It helps in analyzing a signal in a different domain which is much simpler to understand and manipulate. You can't see how much noise is present in a signal when analyzing in the time domain. But after the transform, you can get what frequencies are present in your signal. FT is not only used in analyzing signals, but also in image compressions. It decomposes the image into sine or cosine components into the frequency domain. It gives an image that has a spectrum of wavelengths. Hence, it's pretty much clear that FT is a very useful tool not just in the communication domain, but also in computing.
<h3>Explanation of FT</h3>
The Fourier series is defined as any function that is integrable can be represented as an infinite sum of sines and cosines.

![image](https://user-images.githubusercontent.com/63239714/124540417-fc771a00-de3c-11eb-8d68-56cc39c919f4.png)

where Tk is a continuous function.

The Fourier transform is an upgraded version of the Fourier series. It is defined as -

![image](https://user-images.githubusercontent.com/63239714/124540491-203a6000-de3d-11eb-87e5-73d08fcf612c.png)

where x(t) is any integrable continuous function and X(f) is the FT of x(t) in the frequency domain.

The inverse transform is given by -

![image](https://user-images.githubusercontent.com/63239714/124540522-2f211280-de3d-11eb-9e48-0ac92d84e779.png)

The term e^-j2(pi)ft and e^-j2(pi)ft are Euler's representation-

**e^jx = cos(x) + j*sin(x)**

When the Fourier transform is represented into discrete parts, the Fourier Transform is called the Discrete Fourier Transform (DFT). For this article, we will be discussing the Fast Fourier Transform algorithm and its implementation.
<h3>Fast Fourier Transform (FFT)</h3>
The FFT is a very efficient algorithm for calculating the DFT of a continuous signal and hence the name, Fast Fourier Transform. The working of this algorithm is not that complex. What it does is decomposes the DFT recursively into smaller DFT so that the computation required is very sublime. This method enables the algorithm to achieve a time complexity of O(nlogn), where n is the size of data. The reason it can break down the DFT even further is because of the symmetrical property of DFT.

![image](https://user-images.githubusercontent.com/63239714/124540795-c71efc00-de3d-11eb-8665-699a5b5bc33f.png)

where X is the DFT of any x(t) continuous periodic function.

So as the DFT is symmetric, you don't need to calculate its complementary part because it would be equal. Hence, by this method, the algorithm can achieve such fast computations. This reduction in the computation is highly significant because when the size of the data 'n' is large, the time required would be quite large without FFT.

The implementation of the FFT is available on this GitHub repo. 

<h3>Credits</h3>
https://ai-pool.com/a/s/introduction-of-fast-fourier-transformation--fft
