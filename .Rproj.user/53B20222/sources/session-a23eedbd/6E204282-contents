


library(terra)

# Define the COG URL
cog_url <- "https://knb.ecoinformatics.org/knb/d1/mn/v2/object/urn%3Auuid%3A199c940d-3342-442a-8e2b-4099ca07de69/ santa_barbara_coast_iceplant_locations_2020_west_crs26910"

# Open the COG
r <- rast(cog_url)

# Get the extent and resolution
ext_r <- ext(r)
res_r <- res(r)
height <- nrow(r)

# Fix: Compute ymin for the bottom half correctly
bottom_half_ymax <- ymax(ext_r) - (height / 2) * abs(res_r[2])  # Use absolute value of res

# Define the correct extent for cropping
bottom_half_extent <- ext(xmin(ext_r), xmax(ext_r), ymin(ext_r), bottom_half_ymax)

# Crop to the bottom half and plot
bottom_half <- crop(r, bottom_half_extent)
plot(bottom_half)
