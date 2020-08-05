# NeRF-W Project Website

## Adding videos

Large blobs such as videos are poorly supported in Git. For versioning videos,
we use [`git lfs`](#), a git plugin for large file storage. While this enables
Github to *store* a video, it does not make the video easily accessible from
the web. For *hosting*, we use Google Cloud Storage.

Here are the steps for adding a new video,

1. Install `git lfs` on your system. This only needs to be done once. Follow
   [instructions here](https://git-lfs.github.com/).
1. Add the video to this repository. If it's a `.mp4` or `.webm` file, it'll
   automatically be tracked by `git lfs`. If not, add the filetype to
   `.gitattributes` in this repository.
1. Use your normal `git` workflow to push changes to Github. When referring to
   videos in HTML, use links like
   `https://storage.googleapis.com/nerf-w-public/videos/...` instead of
   `/videos/...`. Note that **VIDEOS WILL NOT LOAD** until you complete the
   following steps.
1. Upload the `videos/` folder in this repository to the `nerf-w-public` GCS
   bucket. Only owners will have write access. You can upload videos with your
   web browser from
   [here](https://pantheon.corp.google.com/storage/browser/nerf-w-public).
