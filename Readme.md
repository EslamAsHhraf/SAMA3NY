# 📶 SAMA3NY

<div align="center">

<img height=500px src="https://cdn.dribbble.com/users/945078/screenshots/2863933/no-signal___2x.gif">
<div align="center"  width=10%>

### "Don't Worry, Your Message Will Be Sent 🔊"

</div>
</div>

<hr style="background-color: #4b4c60"></hr>

## 📝 Table of Contents

- <a href ="#about"> 📙 Overview</a>
- <a href ="#Started"> 💻 Get Started</a>
- <a href ="#work"> ⚒️ Work Explanation</a>
- <a href ="#Contributors"> ✨ Contributors</a>
- <a href ="#License"> 🔒 License</a>
<hr style="background-color: #4b4c60"></hr>
<a id = "about"></a>

## 📙 Overview

<ul>
 <li>
It is required to modulate three speech signals using the following scheme:

<div align="center">
<br>
<img width="500" src="https://user-images.githubusercontent.com/71986226/217121669-1b456300-48b1-4dcc-886f-93a8e3af40f6.png" >
</div>
<br>
and then perform synchronous demodulation.
</li>
<br>
<li>
Then do the following operation:

<ol>
<br>
<li>
	Obtain the modulated signal. Plot it in time domain. Plot its magnitude spectrum
</li>
<li>
Perform synchronous demodulation to restore the three signals.
</li>
<li>
		Perform demodulation three times with phase shifts of 10, 30, 90 degrees for both carriers.
</li>
<li>
		For x_1 (t), perform demodulation two times with a local carrier frequency that is different by 2 Hz and 10 Hz from its carrier frequency.
</li>

</ol>
</li>
<li> <a href="https://github.com/ZiadSheriif/SAMA3NY/blob/main/project.docx">Project Description</a></li>
</ul>
<hr style="background-color: #4b4c60"></hr>
<a id = "Started"></a>

## 🚀 Get Started

<ol>
<li>Clone the repository.

<br>

```sh
git clone https://github.com/ZiadSheriif/SAMA3NY
```

</li>
<li>Put Inputs in folder </li>
<br>

``` sh
cd ./signals
```

</li>
<li>Run File</li>
<br>

``` sh
cd ./project.m
```

</li>
<li>Output will be in folder </li>
<br>

``` sh
cd ./Output_signals
```

</li>
</ol>

<hr style="background-color: #4b4c60"></hr>


<a id ="work"></a>

## 👷🏼 Work Explanation

### Input signals

> Firstly, we read three signals with different sounds and make them have the same frequency sampling =250000 by make resemble to them and find the length of each one along with max length in-order to be able to sum all modulated signal of each input. We make all audios have the same length by adjusting all of them by adding zero to make have same length. Secondly got time and frequencies intervals. Then we calculated omega (ω1, ω2) by ω=2*pi*const in frequency domain. Then we got carrier in cos and sin domain 
Carrier Signal One=cos (2*pi* ω1) 
Carrier Signal Two=sin (2*pi* ω2)
<br>
<table>
<tr>
<th >
<div  align="center">
<strong>
Signal 1
</strong>
</div>
</th>
<th>
<div  align="center">
<strong>
Signal 2
</strong>
</div>
</th>
<th>
<div  align="center">
<strong>
Signal 3
</strong>
</div>
</th>
</tr>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217222582-ae79fd8f-99bb-4d7b-8010-1b3e024882d4.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217222763-a91bfc2f-a14c-4ede-b24e-e02b5aed4761.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217222805-5bdda761-b810-4e59-9fd1-92dfecfb6abe.png">
</td>

</tr>
</table>

### Modulated signal:

<ol>
<li>
Calculate modulated signal by multiplying signal and carrier
</li>
<li>
Calculate Fourier transform of modulated signal returned from step 1
</li>
<li>
Calculate phase of modulated signal returned from step 1
</li>
<li>
Sum all modulated signals of all audios
</li>
<li>
FFT to summation of modulated signals
</li>
<li>
Calculate phase of modulated signals
</li>
<li>
Calculate frequency band pass which is used in de-modulation
</li>
</ol>

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217224606-3307e139-83a1-406f-b6ae-4da97931b544.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217224634-dbfd5ad9-6215-4545-89e5-818c8222a580.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217224649-b1e83f5a-943d-4b2d-80d2-4eb6a8cc0665.png">
</td>

</tr>
</table>

### De-modulation: 

<ol>
<li>
Calculate demodulated signal by multiplying carrier and modulation signal
</li>
<li>
Calculate low pass filter used frequency sampling.
</li>
<li>
Perform demodulation three times with phase shifts of 10, 30, 90 degrees for both carriers 

> **Note**: (before each phase shift calculate carrier phase).
</li>
<li>
Perform demodulation two times with a local carrier frequency that is different by 2 Hz and 10 Hz from its carrier frequency.
</li>
</ol>

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217225512-9a5e7d8b-e78a-4d59-b8e9-c370c574b941.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217225595-af0d2f40-ce55-4746-a317-6124d61ce782.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217225664-254a6957-a752-4e92-92b1-c151f4430710.png">
</td>

</tr>
</table>

<div align="center">
<hr  width="60%" style="background-color: #4b4c60"></hr>
</div>

### 💻 Demodulation with phase shift 10:

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217227859-fa5de52a-c4dc-4587-9790-50b8dabf9147.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217227879-be9166e9-8cec-42ed-80e7-2479adbe6541.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217227905-0bd4c3e4-a024-4baf-afdd-4dce3987364d.png">
</td>

</tr>
</table>

> **Note**: Interference in sounds between signal 2 and signal 3 when make demodulation to them.
Signal 1 become little weaker.

<div align="center">
<hr  width="60%" style="background-color: #4b4c60"></hr>
</div>

### 💻 Demodulation with phase shift 30:

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217227933-ef3e256a-d86c-43e0-a725-46b9f3ba0cbd.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217227960-3d8d5db1-dc00-4580-a053-47aeaef69fb6.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217227980-75965f11-f553-448c-ba33-297be61c9fd2.png">
</td>

</tr>
</table>

> **Note**: More Interference in sounds between signal 2 and signal 3 when make demodulation to them.
Signal 1 become Weaker.
<div align="center">
<hr  width="60%" style="background-color: #4b4c60"></hr>
</div>

### 💻 Demodulation with phase shift 90:

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217228005-f574e9f6-b19f-405d-a5d2-54ffa1151176.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217228037-845239a5-32bc-41be-a5ca-47a7fb6cc326.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217228061-08cd0296-e664-42c2-b15d-28e7db2f3314.png">
</td>

</tr>
</table>

> **Note**: When make demodulation to signal 3 output is signal 2 and make demodulation to signal 2 output is signal3 
Signal 1 be equal zero (no sound).
<div align="center">
<hr  width="60%" style="background-color: #4b4c60"></hr>
</div>

### 💻 Demodulation with a local carrier frequency that is different by 2 Hz:

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217228099-bbc2f931-870e-4d8a-b97d-78a323cc1bdd.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217228123-311d5957-066f-430f-ab1a-4d6fab377b19.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217228151-9473b2b3-80e6-496e-88d1-644e43fa4ba8.png">
</td>

</tr>
</table>

> **Note**: Interference in sounds between signal 2 and signal 3 when make demodulation to them.
All signals have been occurred distortion on them.
<div align="center">
<hr  width="60%" style="background-color: #4b4c60"></hr>
</div>

### 💻 Demodulation with a local carrier frequency that is different by 10 Hz:

<table>
<tr>
<td>
<img  src="https://user-images.githubusercontent.com/71986226/217228174-0c67e49f-8613-4dd3-8024-9b56736fdc32.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217228198-b12158f3-fb97-4a06-8696-43c98a0d193f.png">
</td>
<td>
<img src="https://user-images.githubusercontent.com/71986226/217228217-4c42b44c-54b6-434c-b32d-ab95debe8883.png">
</td>

</tr>
</table>

> **Note**: More Interference in sounds between signal 2 and signal 3 when make demodulation to them.
All signals have been occurred more distortion on them.

<hr style="background-color: #4b4c60"></hr>


<a id ="Contributors"></a>

## 👑 Contributors

<br>
<table >
  <tr>
        <td align="center"><a href="https://github.com/ZiadSheriif"><img src="https://avatars.githubusercontent.com/u/78238570?v=4" width="150px;" alt=""/><br /><sub><b>Ziad Sherif </b></sub></a><br /></td>
        <td align="center"><a href="https://github.com/EslamAsHhraf"><img src="https://avatars.githubusercontent.com/u/71986226?v=4" width="150px;" alt=""/><br /><sub><b>Eslam Ashraf</b></sub></a><br /></td>
  </tr>
</table>

<hr style="background-color: #4b4c60"></hr>

<a id ="License"></a>

## 🔒 License

> **Note**: This software is licensed under MIT License, See [License](https://github.com/ZiadSheriif/SAMA3NY/blob/main/LICENSE) for more information ©SAMA3NY.
