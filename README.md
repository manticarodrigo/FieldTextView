# FieldTextView
A UITextView class that behaves like a UITextField, but with multi-line word wrapping.

<H2>SETUP</H2>
* Drop FieldTextView.swift file into project folder and add to project.
* Create a UITextField object and set it's class to FieldTextView.
* Set FieldTextView.placeholder text in viewDidLoad().
* Set FieldTextView.textAlignment to desired value.
* Set your UITextView delegate in viewDidLoad() and implement the methods:

```swift

func textViewDidChange(_ textView: UITextView) {
    if let fieldTextView = textView as? FieldTextView {
        fieldTextView.placeholderLabel.isHidden = !textView.text.trimmingCharacters(in: .whitespaces).isEmpty
    }
}

func textView(_ textView: UITextView, shouldChangeTextIn range: NSRange, replacementText text: String) -> Bool {
    if let fieldTextView = textView as? FieldTextView {
        if text == "\n" {
            fieldTextView.resignFirstResponder()
            return false
        }
    }
    return true
}

```
* That's it! Enjoy :)
