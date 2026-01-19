# postcards
Make a postcard site

## Overview

This repository contains an R script for generating beautiful postcard-style personal websites using the [postcards](https://github.com/seankross/postcards) R package.

## Prerequisites

- R (version 3.6 or higher)
- The following R packages will be automatically installed when running the script:
  - `postcards`
  - `rmarkdown`

## Usage

### Interactive Mode

Run the script without arguments to use interactive mode:

```bash
Rscript generate_postcard.R
```

You'll be prompted to enter:
- Template name (jolla, jolla-blue, trestles, onofre, or solana)
- Your name
- Email address
- GitHub username
- Twitter username

### Command Line Mode

Create a new postcard with a specific template:

```bash
Rscript generate_postcard.R create [template]
```

Example:
```bash
Rscript generate_postcard.R create jolla
```

Render an existing postcard to HTML:

```bash
Rscript generate_postcard.R render [file.Rmd]
```

Example:
```bash
Rscript generate_postcard.R render index.Rmd
```

### Using in R

You can also source the script in R and use its functions directly:

```r
source("generate_postcard.R")

# Create a postcard
create_postcard(
  template = "jolla",
  title = "John Doe",
  author = "John Doe",
  email = "john.doe@example.com",
  github = "johndoe",
  twitter = "johndoe"
)

# Render the postcard
render_postcard("index.Rmd")
```

## Available Templates

- **jolla**: A simple template with a large profile photo
- **jolla-blue**: A blue variation of the jolla template
- **trestles**: A two-column layout with photo on the left
- **onofre**: A minimalist single-column design
- **solana**: A template with a sidebar layout

## Example

An example postcard file (`example_postcard.Rmd`) is included in this repository. You can use it as a starting point for your own postcard.

## Customization

After generating a postcard:

1. Edit the `.Rmd` file to customize your content
2. Add your photo as `image.jpg` in the same directory (or update the `image` field in the YAML header)
3. Render the postcard to HTML using `rmarkdown::render()` or the provided script

## Output

The script generates:
- An R Markdown file (`.Rmd`) with your postcard content
- When rendered, an HTML file that can be hosted as a static website

## Hosting

You can host your postcard on:
- GitHub Pages
- Netlify
- Any static site hosting service
