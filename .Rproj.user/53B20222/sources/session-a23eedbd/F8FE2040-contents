
say_aloha <- function(name, print = TRUE) {

  message <- paste("Aloha,",
                   name,
                   emo::ji("palm_tree"),
                   emo::ji("sunny"),
                   emo::ji("ocean"))

  if (print) {
    cat(crayon::bgGreen(message))
  }

  invisible(message)
}



#' Crop raster to top half
#'
#' @param x A URL to a COG or SpatRaster
#'
#' @return A cropped raster
#' @export
crop_half <- function(x) {
  if (is.character(x)) {
    x <- terra::rast(x)
  }
  ext_x <- ext(x)
  res_y <- abs(res(x)[2])
  height <- nrow(x)
  ymin_crop <- ymin(ext_x) + (height / 2) * res_y
  crop_ext <- ext(xmin(ext_x), xmax(ext_x), ymin_crop, ymax(ext_x))
  terra::crop(x, crop_ext)
}
