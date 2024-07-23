# Stimulus Mask Demo

A Rails application demonstrating the use of Stimulus for dynamic input masking using the `stimulus-mask` package with `esbuild` for JavaScript bundling.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Setup](#setup)
- [Running the Application](#running-the-application)
- [Contributing](#contributing)
- [License](#license)

## Installation

To get started with this application, clone the repository and install the necessary dependencies:

```bash
git clone https://github.com/rodrigotoledo/stimulus_mask_demo.git
cd stimulus_mask_demo
bundle install
npm install
```

## Usage

This application uses `stimulus-mask` to dynamically mask input fields. The `mask_controller.js` from `stimulus-mask` is used to apply the masks.

## Setup

1. Install Stimulus Mask:

Add `stimulus-mask` using npm:

```bash
npm add stimulus-mask
```

2. Import and Register Mask Controller:

Import and register the `mask_controller.js` in your Stimulus application. Edit `app/javascript/controllers/index.js`:

```js
import MaskController from "stimulus-mask"
application.register("mask", MaskController)
```

3. Use the Mask Controller in your Views:

Add the `data-controller` attribute to your input fields in the Rails views to apply the mask. For example, in `app/views/home/index.html.erb`:

```html
<h1>Stimulus Mask Demo</h1>
<div data-controller="mask">
  <input type="text" data-action="input->mask#mask" data-mask-format="999.999.999-99" placeholder="CPF" />
  <input type="text" data-action="input->mask#mask" data-mask-format="99\\9.999.999-99" placeholder="CPF with number 9" />
  <input type="text" data-action="input->mask#mask" data-mask-format="####-####" placeholder="Something..." />
  <input type="text" data-action="input->mask#mask" data-mask-format="\\#9-999\\#" placeholder="Literal # and digits" />
</div>
```

4. Start the server:

Something important is the project use the `esbuild`, so you need run project locally with:

```bash
bin/dev
```

Visit `http://localhost:3000` to see the application in action.

5. Contributing:

Bug reports and pull requests are welcome on GitHub at https://github.com/rodrigotoledo/stimulus_mask_demo. This project is intended to be a safe, welcoming space for collaboration.

6. License:

This project is licensed under the MIT License.

Feel free to customize the `README.md` further based on additional details and specific configurations of your project.