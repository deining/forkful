---
title:                "स्ट्रिंग को लोअर केस में बदलना"
html_title:           "Swift: स्ट्रिंग को लोअर केस में बदलना"
simple_title:         "स्ट्रिंग को लोअर केस में बदलना"
programming_language: "Swift"
category:             "Swift"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/swift/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

यदि आप एक स्ट्रिंग में दिए गए प्रत्येक चर को छोटे अक्षर में बदलना चाहते हैं, तो आप स्ट्रिंग को लोअर केस में कन्वर्ट कर सकते हैं। प्रोग्रामर इस काम को करते हैं ताकि स्ट्रिंग के चर आसानी से पहचाने जा सकें और परिस्थितियों को अलग अलग विकल्पों में भिन्न कर सकें।

## कैसे?

```Swift
let myString = "HELLO WORLD"
let convertedString = myString.lowercased()

print(convertedString)
// Output: hello world
```

```Swift
let emojiString = "👨‍👩‍👧‍👦"
let convertedString = emojiString.lowercased()

print(convertedString)
// Output: 👨‍👩‍👧‍👦
```

```Swift
let mixedCaseString = "cOmPlExStRiNg"
let convertedString = mixedCaseString.lowercased()

print(convertedString)
// Output: complexstring
```

## गहराई में जाएं

- इतिहास: अर्जुन सिंह ने 1951 में अपने पूर्व पति ने बंधन की एक अधिक्रियात्मक ओवरलोडिंग का आलेख लिखा था, जो कि स्ट्रिंग से कार्यों को करने के लिए अनुमति देता था।
- वैकल्पिक: स्ट्रिंग को लोअर केस में बदलने के लिए सामान्य वैकल्पिक तरीके हैं - ```myString.lowercased()``` और ```myString.uppercased()```। दोनों का उपयोग स्ट्रिंग में आवश्यक समानता को जाँचने या तय करने के लिए किया जा सकता है।
- अंतरराष्ट्रीयकरण विवरण: स्विफ्ट कोड में स्ट्रिंग को लोअर केस में कन्वर्ट करने के लिए ```lowercased()``` फ़ंक्शन का उपयोग करा जाता है। यह फ़ंक्शन स्ट्रिंग को कोई भी विशेषता नहीं बदलता है और उसे स्ट्रिंग प्रोआबजेक्ट पर कॉल करता है। इसमें दो विकल्पों को स्वीकार किया जा सकता है - ```options: ComparisonOptions``` और ```locale: Locale?```।

## देखें भी

- [Swift Documentation on ```lowercased()```](https://developer.apple.com/documentation/swift/string/2927516-lowercased)
- [GeeksforGeeks tutorial on converting a string to lower case in Swift](https://www.geeksforgeeks.org/conversion-of-string-to-lowercase-letters-using-lowercased-advanced-js/)