Keys
====

Easy keyboard-handling for jQuery. Map key codes to human-readable
names and simplify meta-key handling.

### Example usage

Define your key mappings in a key handler function. A switch statement
lets you use multiple cases to catch named keys or key combinations.
Return true on a successful match to prevent further event propagation,
or false to allow it to be caught by any other handlers.

    keys.addHandler(function(key){
      switch (key) {
        case 'space': /* Do this */ break;
        case 'enter': /* Do that */ break;
        default:      return false; break;
      }
      return true;
    });

Map multiple keys or combos to a single action:

    keys.addHandler(function(key){
      switch (key) {
        case 'shift-tab':
        case 'left':
        case 'h':
          // Go left
          break;

        case 'up':
        case 'k':
          // Go up
          break;

        case 'tab':
        case 'right':
        case 'l':
          // Go right
          break;

        case 'down':
        case 'j':
          // Go down
          break;

        case 'space':
        case 'enter':
          // Perform an action
          break;

        default:
          return false;
          break;
      }

      return true;
    });

### Example names

Some example key and combo names are:

    '0'   # Numbers 0-9
    'a'   # Lowercase letters a-z
    'A'   # Uppercase letters A-Z
    'tab' # Special keys

    # Crazy meta key combos (always in this order)
    'cmd-ctrl-alt-shift-enter'

    # For an uppercase letter 'shift' is discarded
    'ctrl-W'

    # Unmatched keys return a key code in square brackets.
    # These are usually punctuation keys where the code
    # can't be reliably mapped to a name.
    '[52]'

