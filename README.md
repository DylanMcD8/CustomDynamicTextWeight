# CustomDynamicTextWeight
Dynamic Text is a great way to increase your app's accessibilty, but it comes with a caveat: aside from Headline, all font sizes are weighted in Regular! In my opinion, this is terrible. I've seen some other functions out there that involve taking the dynamic text's descriptors or whatever, but those result in terribly innacurate sizes. This solution is very simple and allows for dynamic changing of sizes if the user changes their preferred text size while your app is running.

Just add this function outside a class somewhere in your project:

`func makeDynamic(label: UILabel?, style: UIFont.TextStyle, weight: UIFont.Weight) {
    if let label = label {
        label.font = UIFont.preferredFont(forTextStyle: style)
        label.font = UIFont.systemFont(ofSize: label.font.pointSize, weight: weight)
    }
}`

And to use: `makeDynamic(label: notesTitle, style: .footnote, weight: .medium)`

Free to everyone, no credit needed. If you have suggestions for improving, please open an Issue or PR.

