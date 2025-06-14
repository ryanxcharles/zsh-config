i'd like to make a shortcut in zsh that works in the following way.

i often do:

```zsh
git add . && git commit -m "my commit message"
```

can i turn this into a shortcut? ideally, it would like even simpler:

```zsh
gacm my commit message
```

is this possible? how do i do this?

# === ASSISTANT ===

Absolutely, you can achieve this in **zsh** (and bash, too) by creating a function in your shell config (usually `~/.zshrc`). Here’s how you can do exactly what you described:

---

### 1. Open your `~/.zshrc`:

```zsh
nano ~/.zshrc
```

---

### 2. Add this function at the end:

```zsh
gacm() {
  git add .
  git commit -m "$*"
}
```

**Explanation:**
- `$*` combines all the arguments you pass to the function into one string, so `gacm my commit message` becomes `"my commit message"`.

---

### 3. Save and reload your config:

```zsh
source ~/.zshrc
```

---

### 4. Done!  
Now you can use:

```zsh
gacm my commit message
```

and it’ll run:

```zsh
git add .
git commit -m "my commit message"
```

---

#### **Bonus: Suggested improvement**

If you want a shorthand for committing **all staged changes only** (without auto-adding), you could do:

```zsh
gcm() {
  git commit -m "$*"
}
```

But for your use-case, `gacm` as above is exactly what you want.

---

**Let me know if you want any more git or zsh shortcuts!**

# === USER ===

i am using oh-my-zsh, does it have other shortcuts i should know about?
