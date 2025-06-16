# Stats Strided DNANMSKRange 📊

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Downloads](https://img.shields.io/badge/downloads-1000%2B-yellow)

Welcome to the **Stats Strided DNANMSKRange** repository! This project provides a simple and efficient way to calculate the range of a double-precision floating-point strided array while respecting a mask and ignoring NaN values. 

You can find the latest releases [here](https://github.com/Tahmid-Ohara/stats-strided-dnanmskrange/releases). Please download the necessary files and execute them to get started.

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Examples](#examples)
5. [API Reference](#api-reference)
6. [Contributing](#contributing)
7. [License](#license)
8. [Acknowledgments](#acknowledgments)

## Introduction

In statistics, the range of a dataset is a measure of dispersion, representing the difference between the maximum and minimum values. This project focuses on calculating the range for strided arrays, which are commonly used in performance-sensitive applications. The added complexity of handling NaN values and masks makes this tool especially useful for data analysis in JavaScript and Node.js environments.

### Key Features

- Calculate the range of strided arrays.
- Ignore NaN values in calculations.
- Support for masking to include or exclude specific elements.
- Built with performance in mind.

## Installation

To install the Stats Strided DNANMSKRange library, you can use npm:

```bash
npm install stats-strided-dnanmskrange
```

After installation, you can import it into your JavaScript or Node.js project:

```javascript
const { range } = require('stats-strided-dnanmskrange');
```

## Usage

Using the Stats Strided DNANMSKRange library is straightforward. Here’s a basic example of how to use the `range` function:

```javascript
const { range } = require('stats-strided-dnanmskrange');

const array = new Float64Array([1.0, 2.0, NaN, 4.0, 5.0]);
const mask = new Uint8Array([1, 1, 0, 1, 1]); // Mask to include elements 0, 1, 3, 4

const result = range(array, mask);
console.log(result); // Output: { min: 1.0, max: 5.0, range: 4.0 }
```

## Examples

### Basic Range Calculation

```javascript
const { range } = require('stats-strided-dnanmskrange');

const data = new Float64Array([10.0, 20.0, 30.0, NaN, 50.0]);
const mask = new Uint8Array([1, 1, 1, 0, 1]);

const result = range(data, mask);
console.log(`Min: ${result.min}, Max: ${result.max}, Range: ${result.range}`);
// Output: Min: 10.0, Max: 50.0, Range: 40.0
```

### Handling All NaN Values

```javascript
const { range } = require('stats-strided-dnanmskrange');

const data = new Float64Array([NaN, NaN, NaN]);
const mask = new Uint8Array([1, 1, 1]);

const result = range(data, mask);
console.log(result); // Output: { min: NaN, max: NaN, range: NaN }
```

## API Reference

### `range(array, mask)`

Calculates the minimum, maximum, and range of a strided array while respecting a mask.

#### Parameters

- `array`: A `Float64Array` containing the data.
- `mask`: A `Uint8Array` that indicates which elements to include (1) or exclude (0).

#### Returns

An object containing:

- `min`: The minimum value in the array.
- `max`: The maximum value in the array.
- `range`: The difference between `max` and `min`.

## Contributing

We welcome contributions to enhance the functionality and performance of Stats Strided DNANMSKRange. If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch to your fork.
5. Open a pull request.

Please ensure that your code adheres to the existing style and includes appropriate tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

We would like to thank the contributors and the open-source community for their support and inspiration. Your efforts make projects like this possible.

For further details and updates, please visit the [Releases](https://github.com/Tahmid-Ohara/stats-strided-dnanmskrange/releases) section.