# Android-gallery
Simple and standard android gallery that allows you to view media content fullscreen one by one including video player for videos.
Android gallery includes all usual gestures like swipe to dismiss, pinch to zoom, quick scaling by double tap and other. 

## Install
Under constructuion
## Usage
All you need to create list of your media content is URL of each of image/video. 
Just create list of `Media`:
```
fun createGallery() {
  val listOfMedia = arrayListOf(
            Media(
                    thumbnailUrl = "http://mazwai.com/system/posts/videos/000/000/183/poster_3/a_sky_full_of_stars.png", 
                    type = MediaType.VIDEO,
                    url = "http://mazwai.com/system/posts/videos/000/000/183/original/a_sky_full_of_stars.mp4"
            ),
            Media(
                    thumbnaulUrl = "https://images.pexels.com/photos/459225/pexels-photo-459225.jpeg",
                    type = MediaType.IMAGE,
                    url = "https://images.pexels.com/photos/459225/pexels-photo-459225.jpeg"
            ))
}
```  
Pass created list to `GalleryFragment` with the position of image you want to view. 
After that you can show fragment by passing `FragmentManager` and fragment tag to `show` method:
```
fun onImageClick(position: Int) {
  GalleryFragment
              .create(listOfMedia, position)
              .show(supportFragmentManager, "fragment_tag_gallery")
}
```
For more information just look throw the sample.
## Used libraries
* [PhotoView](https://github.com/chrisbanes/PhotoView) for images viewing
* [ExoPlayer](https://github.com/google/ExoPlayer) for videos playing
* [Glide](https://github.com/bumptech/glide) for media content loading
