# Inconsistent Image Order with Expo ImagePicker Multiple Selection

This repository demonstrates a bug in Expo's ImagePicker library where the order of selected images is not consistent when selecting multiple images. The order of images in the result array does not always match the order in which the user selected them.  This inconsistency can lead to unexpected application behavior, especially when image order is significant (e.g., slideshows, image processing pipelines).

## Bug Reproduction

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the application using `expo start`.
4. Select multiple images from your device's gallery.
5. Observe that the displayed images might not be in the same order as selected.

## Solution

This repository provides a potential solution. The solution is implemented in `ImagePickerBugSolution.js` using an additional array which tracks the order of selection. The ImagePicker's `assets` array is then mapped to this order array, restoring the selection order. The solution modifies the standard behavior by associating order indices with selected assets which are then used to ensure consistent display order.  Further investigation into the root cause of the inconsistent behavior is warranted. 