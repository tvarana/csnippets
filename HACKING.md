## Coding Style

I use and prefer Linux style over all but may be switching to GNU coding standards since I'm starting to like them.

Use tabs of 8 width and braces in line not after.  If you feel the code looks like spaghetti, use astyle to format it.

### Braces

#### If statements

Braces should be placed in the same line:
```c
if (x) {
	if (y)
		z();
}
```
Or:
```c
if (x)
	if (y)
		z();
```

Nested if statements can be confusing, so seperate each condition in a new line:
```c
if (foo) {
	bar();
	if (baz && whatever
		(|| whatsoever
		 && lol) {
		... some interesting code ...	 
	}
```

#### Loops

Same as if statements:
```c
int i;

for (i = 0; i < whatever; i++)
	if (haha)
		ok();
```

#### Functions
Put braces after definition:
```c
void foo(void)
{
	... do some nasty stuff ...
}
```

It's okay to not use the extern keyword to declare:
```c
extern void foo(void);
```
or:
```c
void foo(void);
```
is fine too.

Make the function file-scope whenever possible (if you're not going to use it in other files):
```c
static void bar(void)
{
	... lots of code ...
}
```

### Gotos

Feel free to use goto's whenever possible, they're helpful but try not to make it look like spaghetti
It's hard to follow goto statements so try to avoid them whenever you think you don't really need it.
```c
static void baz(void)
{
	int i = 0;

	for (i = 0; i < n; i++)
		if (whatever[i] == some_interesting_value)
			goto done;

done:
	haha();
}
```

Comment code you feel confusing.

### Commits

Please [signoff](http://gerrit.googlecode.com/svn/documentation/2.0/user-signedoffby.html) your commits.

Use [detailed commit messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)

More to come.
