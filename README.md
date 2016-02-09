# github-syntax-highlighting-playground
A place to test github syntax highlighting styles

## Python example
```python
def inference(assignment, var_to_update, value, csp):
    """ Assign VALUE to VAR_TO_UPDATE in ASSIGNMENT. Update domains of
       constrained variables from CSP. If any domains are reduced to 1, also
       inference from them. If any domains are reduced to 0, return False.
       Recursive forward checking.
    """
    assignment[var_to_update] = value
    for constraint in csp[var_to_update]:
        if value not in assignment[constraint]:
            continue
        assignment[constraint] = assignment[constraint].replace(value, "")
        remaining = assignment[constraint]
        if len(remaining) == 1:
            if not inference(assignment, constraint, remaining, csp):
                return False
        elif len(remaining) == 0:
            return False
    return True
```

## Bash example
```bash
[[ $? = 0 ]] && curErr='' || curErr='1'
if [[ $curErr && $lastErr ]]; then # Two consecutive errors
  table=$'(╯ಠ益ಠ)╯彡┻━┻'
elif [[ $curErr ]]; then # One error
  table=$'(╯°□°)╯︵┻━┻ '
elif [[ $lastErr ]]; then # One success
  table=$' ┬──┬ ﾉ(°—°ﾉ)'
else # Two consecutive successes
  table=$'( °—°)   ┬──┬'
fi
lastErr=$curErr
```

## JavaScript example
```javascript
var Gallery = function(className) {
  this.className = className;
  this.images = document.getElementsByClassName(className);
  this.state = -1;

  // this.onclick = this.toggleOn()
  for (var i = 0, img; img = this.images[i]; i++) {
    var gallery = this;
    img.onclick = (function(initialState) {
      return function() { gallery.toggleOn(initialState); }
    }(i));
  }
}
```
