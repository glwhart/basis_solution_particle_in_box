# Revision History

## Revision 0.0.1

- Added history file
- Working from virtualenv 'x'
- Copied over 'setup.py' from practice repo
- Copied over the 'requirements.txt' file
- Copied over the 'setup.cfg' file. Just seems to be settings for the tests
- Copied over 'tox.ini'. Settings for tests and for coverage
- Copied over 'tests/' and 'potentials/' and 'basis/'


Questions to ask Conrad:

? What do I need to do to set up the python? Wasn't there a pip install?
? What is the 'requirements.txt' file for? What scripts need this?
A: This is needed by the CI server. It's referred to in the 'travis.yml' file
? Why is pytest looking in the 782 directory still? Where is that hardwired in?
A: That was because 'pip install -e .' was still active in old virtualenv.
? I didn't copy over basis, and yet everything still works? Is it looking over their for some
reason? The basis package is still installed. Is that related to the virtualenv?
A: Yes
? How do I use the 'setup.py' script? termcolor package still missing. Must need to do something else.
A: 'pip install -e .'

** Made a new virtualenv 'xx'
pytest didn't works so:
- pip install pytest
pytest: couldn't find basis.potential (how did it know to look for that?)
A: was still installed in old virtualenv

* because the tests in 'tests' directior are importing basis.potential
? How do I import that?
A: Apparently 'pytest' will look for a folder with that name at the same level as 'tests/'
A: copied over 'basis/' and the problem went away
- pytest
Now it can't find numpy. Seem like this should have been taken care of by the setup.py script. But
I'm not sure that I've run that and I don't know how...
- chmod +x setup.py
- ./setup.py
Now it's missing termcolor. Don't think that my setup is working
A: 'pip install -e .' in director where 'setup.py'

** Answers
- pip install -e .  # Must look in current directory for package. -e means don't have to reinstall
each time we make an edit
# Because of this, no problems now with termcolor, argparse, etc.

## Revision 0.0.2

Commit adding files from Rev. 0.0.1

- installed 'pip install sphinx'
- installed 'pip install sphinxcontrib-napoleon'
- 'sphinx-quickstart'

## Revision 0.0.3

- Added comments/answers to history file from Conrad and Wiley
- Fixed python 3 bug in one of the unit tests