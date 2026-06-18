# Xiaoge Zhang Homepage

Personal academic homepage and project website source for Xiaoge Zhang.

This repository hosts a Jekyll-based academic website containing the homepage, publication list, and standalone project pages for recent research works in 3D computer vision, neural representations, and 3D compression.

## Available Pages

### Homepage

The homepage presents:

- short biography
- selected publications
- project links
- teaching activities

### Project Pages

Dedicated project pages are available for:

- `DiffCom`: Decoupled Sparse Priors Guided Diffusion Compression for Point Clouds
- `FLaTEC`: Frequency-Disentangled Latent Triplanes for Efficient Compression of LiDAR Point Clouds
- `MaGic-NeRF`: Multimodal Generative Priors and Conditional Flow for Extreme NeRF Compression
- `PGMS`: Pyramidal Gaussian Mixture Splatting for 3DGS Compression

## Repository Structure

- `_pages/` - homepage and standalone project pages
- `_publications/` - publication entries shown on the homepage
- `_includes/` - reusable HTML fragments and custom homepage styling
- `_layouts/` - page layouts
- `images/` - profile photos, publication teasers, and project figures
- `files/` - downloadable assets if needed
- `markdown_generator/` - optional scripts for generating markdown content

## Local Development

We use Jekyll for local preview and development.

### Dependencies

Install Ruby, Bundler, and Node.js first.

On Ubuntu:

```bash
sudo apt update
sudo apt install ruby-dev ruby-bundler nodejs build-essential gcc make
```

On macOS:

```bash
brew install ruby
brew install node
gem install bundler
```

### Install Packages

```bash
bundle install
```

If gem permissions cause issues, install locally:

```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

### Run Locally

```bash
bundle exec jekyll serve -l -H localhost
```

The local preview is then available at:

```text
http://localhost:4000
```

## Updating Content

### Add a Publication

1. Create a new markdown file under `_publications/`
2. Fill in front matter fields such as `title`, `authors`, `venue`, `date`, and `teaser`
3. Optionally add `paperurl`, `projecturl`, and `codeurl`

### Add a Project Page

1. Create a new markdown page under `_pages/`
2. Set a `permalink` in the form `/project/<name>/`
3. Add related assets to `images/projects/<project-name>/`
4. Link the corresponding publication entry through `projecturl`

## Notes

- This website is customized from the Academic Pages Jekyll template.
- Some project pages use custom static HTML layouts for project-style presentation.
- Changes to `_config.yml` require restarting the Jekyll server.

## Acknowledgement

This website is built on top of the Academic Pages template and has been customized for Xiaoge Zhang's academic homepage and research project showcases.
