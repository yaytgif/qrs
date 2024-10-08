# @qifi/generate

<!-- Some beautiful tags -->
<p align="left">
  <a href="https://www.npmjs.com/package/@qifi/generate">
    <img alt="npm" src="https://badgen.net/npm/v/@qifi/generate">
  </a>
  <a href="#usage">
    <img alt="docs" src="https://img.shields.io/badge/-docs%20%26%20demos-1e8a7a">
  </a>
  <a href="https://github.com/sponsors/LittleSound">
    <img alt="docs" src="https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86">
  </a>
</p>

Stream Generated QR Codes for data transmission

## Sponsors

<p align="center">
  <a href="https://github.com/sponsors/LittleSound">
    <img src="https://cdn.jsdelivr.net/gh/littlesound/sponsors/sponsors.svg"/>
  </a>
</p>

<p align="center">
  This project is made possible by all the sponsors supporting my work <br>
  You can join them at my sponsors profile:
</p>
<p align="center"><a href="https://github.com/sponsors/LittleSound"><img src="https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86&style=for-the-badge" /></a></p>

## Usage

```javascript
import {
  createGeneraterANSI,
  createGeneraterUnicode,
  createGeneraterUnicodeCompact,
  createGeneraterSVG,
  createGeneraterQRCodeArray,
} from '@qifi/generate'

const generaterSvg = createGeneraterSVG(new Uint8Array(file.buffer))

const generaterANSI = createGeneraterANSI(new Uint8Array(file.buffer), {
  // Size of each data slice
  indicesSize: 250,
  // Error correction level
  ecc: 'L',
  // Border width
  border: 2,
})

// display QR Code in terminal
for (const blockQRCode of generaterANSI()) {
  console.log(blockQRCode)
}

```