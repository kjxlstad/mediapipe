### Fork of mediapipe with enabled gpu inference for python hand tracking.

I had some troubles trying to configure this, but got it working in the end. Hopefully this can help others doing the similar changes in the future.

#### Changes
- Cuda options and links to nvcc was added to .bazel
- Path to opencv and ffmpeg was configured in workspace
- Build options in /graphs/hand_tracking/ and /python/ was changed to point to the gpu graphs
- Number of hands supported was changed in /graphs/hand_tracking/hand_tracking_desktop_live_gpu.pbtxt
- The hand_landmark_tracking_gpu.pbtxt graph was modified for converting the images from python to gpu buffers
- /python/solutions/hands.py was modified to utilize the gpu graphs
- setup.py points to gpu graphs instead, flags for MESA_EGL_NO_X11_HEADERS and EGL_NO_X11 were also added 
- Paths were uptaed in opencv_linux.build and ffmpeg_linux.build were changed to point to the correct directory.
