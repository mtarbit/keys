Keys
====

Easy keyboard-handling for jQuery. Map key codes to human-readable
names and simplify meta-key handling.

### Example usage

The basic handler pattern is a switch statement with cases catching named 
keys or key combinations. Returning true on a successful match to prevent
further event propogation. Or false to allow the event to continue on to 
any other handlers.

    keys.addHandler(function(key){
      switch (key) {
        case 'space':
          // Do something
          break;

        case 'enter':
          // Do something else
          break;

        default:
          return false;
          break;
      }

      return true;
    });

The switch statement lets you map multiple keys or combos to a single action:

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

