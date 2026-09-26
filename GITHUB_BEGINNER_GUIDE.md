# FIRST-TIME GITHUB GUIDE

## Part A — Create a GitHub account
1. Go to https://github.com/
2. Create/sign in to your account.
3. Choose a professional username you are comfortable putting on your resume and website.

## Part B — Create the repository
1. Click the + icon in the upper-right corner.
2. Click **New repository**.
3. Repository name: `catchment-climate-data-toolkit`
4. Description:
   `Interactive watershed delineation and catchment-area-weighted PRISM climate extraction using Python, USGS NLDI, and NHDPlus.`
5. Set visibility to **Public**.
6. IMPORTANT: because this package already contains README/LICENSE/.gitignore, leave the GitHub initialization checkboxes unchecked.
7. Click **Create repository**.

## Part C — Upload this package
1. Unzip `catchment-climate-data-toolkit.zip` on your computer.
2. In your empty GitHub repository, click **uploading an existing file** (or Add file > Upload files).
3. Open the unzipped project folder.
4. Drag the project files/folders into the GitHub upload area.
5. Commit message: `Initial release of Catchment Climate Data Toolkit`
6. Click **Commit changes**.

If GitHub's browser upload does not preserve an empty-ish folder, that is fine: both `images` and `examples` contain README files so they will upload.

## Part D — Test the notebook
1. Open `Catchment_PRISM_Extractor.ipynb` on GitHub.
2. Copy your GitHub username.
3. Build this URL:
   `https://colab.research.google.com/github/YOUR_USERNAME/catchment-climate-data-toolkit/blob/main/Catchment_PRISM_Extractor.ipynb`
4. Open it.
5. In Colab choose **Runtime > Run all**.
6. Keep the default one-month test period first.
7. Inspect the map carefully: confirm the outlet and watershed are correct.
8. Confirm the downloaded ZIP contains GeoJSON, HTML map, and PRISM CSV.

## Part E — Activate the Colab badge
1. In GitHub open `README.md`.
2. Click the pencil/Edit icon.
3. Replace `COLAB_LINK_AFTER_YOU_UPLOAD` in the first badge with your actual Colab URL.
4. Click **Commit changes**.
5. Use commit message: `Add working Colab launch link`.

## Part F — Update CITATION.cff
1. Open `CITATION.cff`.
2. Click Edit.
3. Replace `REPLACE_WITH_YOUR_GITHUB_REPOSITORY_URL` with your repository URL.
4. Commit: `Update repository citation metadata`.

## Part G — Add your own project screenshots
1. Run the notebook.
2. Take a clean screenshot of the interactive map.
3. Save it as `catchment_map.png`.
4. On GitHub open `images/`.
5. Add file > Upload files.
6. Upload the screenshot and commit.
7. Edit the main README and add:
   `![Example catchment delineation](images/catchment_map.png)`
   below the introduction.

Do the same later with a meteorology figure if desired.

## Part H — Add to your website
Use `website/project-card.html` as the content/template.
Replace:
- `REPLACE_WITH_GITHUB_URL`
- `REPLACE_WITH_COLAB_URL`
- `REPLACE_WITH_YOUR_CATCHMENT_SCREENSHOT`

If your website builder does not accept HTML, copy the text from that file into a normal project card/section and create two buttons manually.

## Part I — How to update the project later (browser-only)
For a small edit:
1. Open the file on GitHub.
2. Click the pencil icon.
3. Edit.
4. Click **Commit changes**.
5. Write a meaningful message such as `Improve PRISM extraction documentation`.

For a replaced notebook:
1. Open the repository.
2. Add file > Upload files.
3. Upload the newer notebook with the exact same filename.
4. GitHub will recognize it as a changed file.
5. Commit with a message such as `Improve catchment weighting workflow`.

## Part J — Good commit-message examples
- `Initial release of Catchment Climate Data Toolkit`
- `Add area-weighted PRISM extraction`
- `Improve NLDI outlet validation`
- `Add example catchment map`
- `Update documentation and citations`
- `Fix missing-data handling`

## Part K — What NOT to upload
Do not upload:
- passwords, API keys, tokens, private data;
- the full PRISM raster cache;
- thousands of `.bil`/`.zip` files;
- unrelated research data that you cannot publicly share.

The included `.gitignore` helps if you later use Git/GitHub Desktop.

## Part L — Suggested GitHub About section
Description:
`Interactive watershed delineation and catchment-area-weighted PRISM climate extraction using Python, USGS NLDI, and NHDPlus.`

Topics:
`hydrology`, `watershed`, `prism`, `nhdplus`, `nldi`, `gis`, `python`, `climate-data`, `water-resources`, `google-colab`

## Part M — Suggested website project text
Title:
`Catchment Climate Data Toolkit`

Subtitle:
`Python · GIS · USGS NLDI · PRISM Climate Data`

Description:
`An interactive hydrologic data workflow that delineates an upstream catchment from an outlet coordinate, maps its drainage network, and extracts catchment-area-weighted daily PRISM precipitation and temperature for hydrologic and water-resources applications.`

Buttons:
`View on GitHub`
`Run in Google Colab`
