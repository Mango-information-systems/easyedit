# easyedit
inline editing of a single an HTMLElement

## rationale

Make any element editable with a click. The input element uses the same font and font-size as the original element. Pressing enter or changing focus saves the new value. Pressing escape returns it to its original value.

## example

    const easyedit = require('easyedit')

    const div = document.createElement('div')
    document.body.appendChild(div)
    div.innerHTML = 'Please edit me.'
    new easyedit(div, { onsuccess: (value) => console.log('div changed to: ' + value));

## API

### constructor easyedit(element, options)

- {htmlElement} element to enable editing
- {object} [options]
- {object} options.styles - additional styles to apply to the inputElement
- {function} options.onedit - editing starts: callback(element, inputElement)
- {function} options.onsuccess - value changed and user pressed enter: callback(value, element)
- {function} options.oncancel - editing canceled with escape: callback(element)
- {function} options.onchange - value was changed (but editing is not done): callback(value, element)

MIT License
(c) 2017 David Figatner (YOPEY YOPEY LLC)