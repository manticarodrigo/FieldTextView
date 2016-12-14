# FieldTextView
A UITextView class that behaves like a UITextField, but with multi-line word wrapping.

<b>SETUP</b>
* Set placeholder label text.
* Set text view text alignment to center, or placeholder label text alignment to desired value.
* Set single-line behavior with the following code (resign responder on return) in your view contoller:
```swift
func textView(_ textView: UITextView, shouldChangeTextIn range: NSRange, replacementText text: String) -> Bool {
    if textView == self.nameTextView, text == "\n" {
        textView.resignFirstResponder()
        return false
    } else {
        return true
    }
}
```
** Remember to set your UITextView delegate
