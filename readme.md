# Satellite Jamming: A Space-Time Fusion Method for Anti-Espionage in Global Navigation Satellite Systems [with MATLAB Code]

Abstract: The Global Navigation Satellite System (GNSS) is an indispensable component for navigation, timing, and synchronization among various critical applications. However, the system is vulnerable to spoofing attacks, which can severely compromise its reliability and security. This paper proposes a novel spatial-temporal fusion global navigation satellite system anti-spoofer method (STAGAS), aimed at enhancing the robustness of GNSS systems against spoofing threats. STAGAS fully leverages the spatial and temporal characteristics of GNSS signals to detect and mitigate spoofing attacks. Through comprehensive evaluation based on real-world scenarios and simulation studies, this method demonstrates exceptional efficacy in detecting and mitigating various spoofing techniques. Research findings indicate that STAGAS is a promising solution for ensuring the security of critical GNSS applications, ensuring the integrity and safety of location-based services.
Keywords: Global Navigation Satellite System (GNSS), Spatial-Temporal Fusion Global Navigation Satellite System Anti-Spoofer Method (STAGAS), Direction of Arrival (DOA), Spatial Smooth MUSIC Algorithm (SSMUSIC), Uniform Linear Array (ULA), Signal-to-Noise Ratio (SNR)
In this context, ensuring the integrity and credibility of GNSS signals has become an urgent task. Global researchers and experts are dedicated to developing robust anti-spoofer technologies to protect GNSS users from malicious signals, ensuring the anti-interference capability of GNSS infrastructure. Spatial-temporal fusion methods are a significant research direction in this field, with the core idea being to enhance the security and reliability of GNSS signals by leveraging unique features in both the spatial and temporal domains.
This paper explores the innovative field of GNSS anti-jamming technology, with a focus on the powerful potential of space-time fusion methods in mitigating the evolving threat of jamming attacks. By integrating spatial and temporal information, this method can detect and counteract jamming attacks in real-time, thereby maintaining the integrity of GNSS navigation and positioning. Through in-depth analysis of existing methods, empirical research, and the introduction of innovative space-time fusion techniques, this paper aims to make significant contributions to advancing robust GNSS anti-jamming solutions.
In the in-depth discussion of space-time fusion methods for GNSS anti-jamming, we will discuss the basic concepts, state-of-the-art technologies, and unique challenges faced by researchers. The insights and research findings presented in this paper are expected to shape the future development of GNSS security, ensuring the continuous reliability and credibility of this key satellite navigation system.
The main contributions of this study are as follows:
1.  
Propose a new GNSS anti-jamming technology based on an antenna array, solving the problem of distinguishing low-power and multipath jamming. This technology enhances signal transmission, reducing multipath effects and jamming impact;
2.  
Improve the spatial spectrum estimation and energy estimation methods, providing DoA and energy indicators, supporting subsequent jamming localization work;
3.  
All operations are performed within the standard frequency parameter range, ensuring compatibility and avoiding receiver failures and tracking issues. Additionally, these operations are designed in simple architectures within GNSS receiver frameworks without introducing unnecessary complexity.
The signal model needs to be clarified that the current antenna array used in the signal model primarily focuses on real signals, which may lead to the generation of deceptive reception modes. However, in practical scenarios, GNSS receivers often face various challenges. These problems stem from multipath signals' deception - multipath signals are highly similar to true signals, posing a significant challenge in detection of deception (especially at the initial stages). To address this, the core goal of this paper is to distinguish between real signals, multipath signals, and false signals when an M-element antenna array receives signals.
In the absence of service signals, this paper assumes that all deceptive signals originate from a single antenna, regardless of whether they come from traditional deception methods or generator-based deception methods. After receiving the signal, preliminary decision processing is conducted at the sampling frequency fs, ultimately forming an M×1 vector of signals:
In this model, the sampling interval is represented as Ts=1/fs, and the complex additive Gaussian white noise vector is denoted as V (nTs). The legitimate signal Sa (nTs) consists of the legitimate signal superimposed by a (θi), where a (θi) represents the steering vector, and Si (nTs) represents the nTs-th legitimate satellite signal. Similarly, the deceptive signal Ss (nTs) and the multipath signal Sm (nTs) are superimposed by deceptive signals and multipath signals, respectively. Na, Nm, and Ns represent the number of legitimate satellite signals, multipath signals, and deceptive signals, respectively. The steering vectors for legitimate signals, multipath signals, and deceptive signals are denoted as a (θi), a (θq), and a (θs), respectively. Additionally, si'(n) represents the i-th deceptive signal, sq''(n) represents the q-th multipath signal, and si (n) represents the i-th legitimate satellite signal. When a GNSS receiver is hijacked, the power ratio of the deceptive signal si'(n) to the legitimate signal si (n) is generally greater than 1, while the power ratio of the multipath signal sq''(n) to the legitimate signal si (n) is generally less than 1.
This paper adopts an Uniform Linear Array (ULA) for the products manufactured by Party B. The steering vector corresponding to the incident angle θk can be represented as follows:
In this study, the spacing between adjacent array elements is set to λ/2 (where λ is the wavelength of the GPS L1 signal, calculated as λ=c/f, with c being the speed of light and f the signal frequency). The signal model employs a uniform linear array (ULA) consisting of 16 omnidirectional sensors.
The proposed anti-jamming strategy mainly achieves two stages: direction of arrival (DOA) estimation and jamming detection and mitigation. In the DOA estimation stage, preprocessing methods are first applied to address the issue of signal model differences caused by factors such as low signal-to-noise ratio (SNR). By using forward / backward spatial smoothing techniques, the correlation between the true signal, jamming signal, and multipath signals is reduced. Subsequently, the preprocessed matrix (PM) derived feature space spectrum is used to determine the direction of arrival (DOA). In the jamming detection and mitigation stage, the original digital baseband signal is processed to perform power calculations, spatial channel separation, monitoring of time-domain cross-correlation peaks, and implementation of jamming countermeasures.
DOA Estimation [3] This stage introduces an improved algorithm for direction of arrival (DOA) estimation. In cases where the signal-to-noise ratio is low, signal preprocessing is particularly important. Through real-time modeling of GNSS signals and self-integration, a difference matrix is designed to reduce noise interference. The Space Smooth MUSIC (SSMUSIC) algorithm is adopted, which reduces the correlation between different locations to improve the accuracy of DOA estimation. This process involves dividing the uniform linear array (ULA) into overlapping grids and performing forward / backward spatial smooth denoising processing.
Signal Preprocessing To address the issues of low signal-to-noise ratio, periodic structure, and autocorrelation in GNSS signals, a covariance matrix is constructed to remove noise components. By utilizing multiple data blocks and corresponding reference data blocks, the estimated covariance is reduced, enhancing the performance of DOA estimation.
The Spatial Smooth MUSIC Algorithm (SSMUSIC) divides uniform linear arrays (ULAs) into overlapping subarrays to improve the accuracy of direction of arrival (DOA) estimation. This process enhances the rank of the covariance matrix by computing the denoised forward/backward spatial smooth matrices, facilitating the identification of DOA for related source signals. Additionally, increasing the number of subarray elements can improve the resolution of DOA estimation.
Feature Space Spectrum Construction (3.1.2) This paper proposes an improved feature space spectrum method that utilizes pre-processed covariance matrices to address issues caused by low signal-to-noise ratio (SNR) and correlated signals. This method eliminates the need for feature decomposition, thereby enhancing computational efficiency. It refines the subspace DOA estimation algorithm, breaking through the Rayleigh limit [5]. By searching for peaks in the newly constructed feature space spectrum and utilizing the derived covariance matrices and corresponding subspaces, the final DOA estimation results are obtained.
The core equations proposed in this scheme include the construction of the covariance matrix (formulas 3 and 4), the denoised forward/backward spatial smooth matrices (formulas 5 and 6), and the feature space spectrum (formula 7). These equations represent key steps in signal preprocessing, spatial smooth MUSIC algorithm (SSMUSIC), and feature space spectrum construction, crucial for achieving robust DOA estimation and subsequent decoy detection.
GNSS Decoy Detection and Mitigation This method has strong performance advantages in the field of GNSS decoy detection and mitigation [6]. Firstly, based on high-resolution DOA estimation results from multiple event sources, a power estimation optimization problem is constructed. Using the denoised sample covariance matrix R (G)xx and relevant theoretical covariance matrices, a non-linear least squares optimization problem is formed, solved through specific matrix operations.
One of the core components of this method is the enhanced power estimation technology, which utilizes the denoised sample covariance matrix to not only improve the accuracy of power estimation but also achieve high-resolution direction of arrival (DOA) estimation [7]. The subsequent GNSS decoy detection process largely relies on the obtained DOA and power features. This paper's method combines cross-correlation and power comparison techniques to extract individual signals through skew projection [8]. Subsequently, a complex beamforming and subspace skew projection interference mitigation system is employed to suppress multipath signals and decoy signals while enhancing genuine signals.
Table 1 Decision and Intervention Rules
Cross-correlation features
Decision outcome
Only one cross-correlation peak appears
Exists only multipath interference
Multiple cross-correlation peaks appear between the highest power signal and other signals.
Only the presence of deceptive signals
Multiple cross-correlation peaks appear; and there is a cross-correlation peak between two specific signals.
The coexistence of deceptive signals and multipath interference
[9] In summary, the GNSS deception detection and mitigation strategy proposed in this paper integrates power estimation, cross-correlation analysis, and interference mitigation methods, aiming to enhance the anti-interference capability and reliability of GNSS systems.
Power comparison optimization problem power comparison solving method cross-correlation operation to summarize the proposed anti-fraud scheme, all steps are described in detail in algorithm 1 of figure 1 [10].
Algorithm 1: GNSS Anti-Fraud Scheme
Direction of arrival (DOA) estimation input: x (・)
1  
Construct the covariance matrix according to formula (5) to suppress noise components;
2  
According to formula (13), reduce the correlation between sources.
3  
Estimate the direction of arrival (DOA) of the signal source through formula (18).
Estimated DoA
Detection and mitigation of input: estimated DoA
1  
Enhanced power estimation is performed using formula (19);
2  
Separate the incident signal according to formula (24);
3  
The mutual correlation results are obtained by formula (25).
4  
Decisions are made based on power comparison and cross-correlation results.
5  
Calculate the output signal based on the decision results.
Figure 1: Algorithm flowchart diagram
Figure 2 shows the relationship between Signal-to-Noise Ratio (SNR) and Root Mean Square Error (RMSE) for direction of arrival (DOA) estimation [10].
Figure 2: Relationship between Signal-to-Noise Ratio and Root Mean Square Error in Wave Direction Estimation
The results have achieved significant achievements in GNSS anti-jamming and jamming suppression based on array antenna signal processing technology. A large number of simulation experiments have verified the effectiveness of the proposed method in distinguishing deceptive signals, multipath interference and real signals.
In Scenario 1, the effective attenuation method forms a depth null in the direction of the deceived signal while retaining the maximum gain of the true satellite signal. The beam structure and cross-correlation data indicate that this method has strong robustness against perturbations.
Figure 1: Spatial Spectrum Estimation Results (Scene 1)
Scene 2: The method was tested in a multipath environment, and the results showed that the proposed direction of arrival (DOA) estimation algorithm could accurately extract the directions of all signals (including multipath signals and legitimate signals). Even under different power levels, this technology could effectively identify multipath interference and distinguish it from true signals.
Figure 2: Spatial Spectrum Estimation Results (Scene 2)
Scene 3 contains deceptive signals, multipath signals and true signals. The proposed method successfully distinguishes the deceptive signals from the multipath signals and satellite signals. Subsequently, the interference suppression technology based on subspace projection is adopted to effectively suppress the deceptive signals and multipath interference while enhancing the real satellite signal.
Figure 3: Spatial Spectrum Estimation Results (Scene 3)
These results collectively demonstrate the robustness and adaptability of the proposed method in various complex scenarios against GNSS spoofing. This research provides a practical and efficient solution for real-world applications, making significant contributions to the field of GNSS security and signal processing.
Figure 3: Beam pattern for verifying the authenticity of a satellite
Conclusion: This study aims to propose a technique based on an array of antennas for spatial-time signal processing, enhancing the security and reliability of GNSS receivers against spoofing attacks. The method includes two stages: Firstly, by improving the feature space generated from preprocessing matrices (PM), the accuracy of direction of arrival (DOA) estimation is enhanced. Leveraging the self-correlation of GNSS signals, through pre-expansion and noise removal techniques, the signal quality is optimized; a rank recovery method is employed to mitigate the correlation between GNSS spoofing signals, multipath signals, and true signals, leading to reduced DOA estimation errors. Secondly, by monitoring cross-correlation peak and power calculation, different scenarios of spoofing issues are addressed. Based on the estimated DOA, signal power is obtained, providing support for cross-correlation analysis, aiding in the identification of spoofing signals. Through beamforming and subspace projection interference suppression techniques, spoofing signals and multipath interference are suppressed, enhancing the real signals.
Simulation results validate the effectiveness of this method, especially in scenarios with signal interweaving and low signal strength. Even under low power spoofing or high power multipath interference scenarios, the proposed anti-spoofing method can effectively detect and alleviate spoofing attacks and multipath interference. It is worth noting that this technology pre-expands the original digital baseband signal of the GNSS receiver, distinguishes spoofing signals from satellite signals based on spatio-temporal differences without the need for additional hardware support.
However, the surge in spatially distributed interference sources (especially considering military electronic countermeasure scenarios) poses a challenge. The flexibility of anti-spoofing systems based on uniform linear arrays (ULAs) is limited in practical deployment, presenting constraints. Although the pre-processing method reduces signal correlation, it sacrifices some effective aperture. With the advancement of current technology, it is necessary to further explore improvements in array antenna topology structure and enhance the capability of spoof detection in actual GNSS applications.
Acknowledgments: First and foremost, I would like to sincerely thank God for his care and endless blessing throughout the entire project process.
I sincerely thank my mentor, Dr. Pushpinder Singh Patheja, for his continuous guidance and active participation in the project, as well as for providing valuable advice that contributed to the successful completion of the project.
I would also like to thank the two reviewers, Dr. Subash C. Patel and Dr. N D Patel, for their expertise and assistance in all aspects of the research.
Finally, I am deeply grateful to my parents for their unwavering support during the tireless efforts and striving for success that I put into this project.
Reference 1
Kundu (D.), Improved MUSIC algorithm for direction of arrival estimation. Signal Processing, 1996. [Google Scholar] [Cross-reference]
2  
Kerns, A.J., Wesson, K.D., Humphreys, T.E.. Commercial GPS Navigation Message Certification Blueprint. IEEE/ION Plans Conference Proceedings, Monterey, CA, USA, May 5-8, 2014, pp. 262-269. [Google Scholar] [Cross-reference]
3  
Broumandan (A.), Jafarnia-Jahromi (A.), Lachapelle (G.). Detection, classification and cancellation (SDCC) receiver architecture for mobile GNSS receivers. GPS Solut, 2014, 19, 475-487. [Google Scholar] [Cross-reference]
4  
McCloud, M.L., Scharf, L.L. A new subspace recognition algorithm for high-resolution direction of arrival estimation. IEEE Antennas and Propagation Letters, 2002, 50, 1382-1390. [Google Scholar] [Cross-reference]
5  
Lavate, T., Kokate, V., Sapkal, A. Adaptive array intelligent antennas for MUSIC and ESPRIT direction of arrival estimation in mobile communication. Proceedings of the 2nd International Conference on Computer and Network Technology, Bangkok, Thailand, April 23-25, 2010, pp. 308-311. [Google Scholar] [Cross-reference]
6  
Zhang (Y.D.), Amin (M.G.), Himed (B.). Sparse Direction of Arrival Estimation Based on Coprime Arrays. Proceedings of the 2013 IEEE International Conference on Acoustics, Speech and Signal Processing, Vancouver, British Columbia, Canada, May 26-31, 2013. [Google Scholar]
7  
Hu (Y.), Bian (S.), Li (B.), Zhou (L.). A novel array-based deception and jamming suppression method for GNSS receivers. IEEE Sens. J., 2018, 18, 2952-2958. [Google Scholar] [Cross-reference]
8  
Ioannides, R.T., Pany, T., Gibbons, G. Global Navigation Satellite System known vulnerabilities, status and potential mitigation techniques. Proc. IEEE, 2016, 104, 1174-1194. [Google Scholar] [Cross-reference]
9  
Hegarty, C.J.; Chatre, E. Global Navigation Satellite System (GNSS) Evolution. Proc. IEEE, 2008, 96, 1902-1917. [Google Scholar] [Cross-reference]
10  
Broumandan (A.), Jafarnia-Jahromi (A.), Dehghanian (V.), Nielsen (J.), Lachapelle (G.) - Handheld receivers for GNSS spoof detection based on signal space correlation. Papers from the PLANS Workshop, Mount Holly, NC, USA, April 23-26, 2012, pp. 479-487. [Google Scholar]
11  
Humphreys, T.E.. Detection strategies for GNSS anti-jamming encryption. IEEE Trans. Aerosp. Electron. Syst., 2013, 49, 1073-1090. [Google Scholar] [Cross-reference]
12  
Wang Fei (Fei Wang), Li Hong (Hong Li). GNSS Spoofing Detection and Mitigation Based on Maximal Likelihood Estimation. 2017. [Google Scholar] [MDPI].
13  
Xu (G.), Shen (F.), Amin (M.), Wang (C.). GNSS Evasion Detection Technology Based on Doppler-Direction Classification and CCPM-PC. Proceedings of the 2018 IEEE/ION Positioning, Navigation and Mapping Workshop (PLANS) - Paper Collection, Monterey, CA, USA, April 23-26, 2018. [Google Scholar]
14  
Zhao Yuqing (Yuqing Zhao), Shen Feng (Feng Shen), Xu Guanghui (Guanghui Xu), Wang Guocheng (Guochen Wang). Special issue on advanced interference mitigation technology for GNSS-based navigation. 2020.
End

## Images

![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](01.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](02.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](03.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](04.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](05.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](06.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](07.jpg)
![[Satellite Jamming] A method for anti-jamming of Global Navigation Satellite System based on space-time fusion](08.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
