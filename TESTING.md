## [Testing](#testing)
  * [Code validation](#code-validation)
  * [Testing User stories](#testing-user-stories)
  * [Responsiveness and Compatibility](#responsiveness-and-compatibility)
  * [Testing performance](#testing-performance)
  * [Testing accessibility](#testing-accessibility)
  * [known bugs](#known-bugs)
  remove button not working in the shopping bag page.

  * page would not render as I had not included 'django.template.context_processors.media' in settings.py so my product which at the time lacked an image caused the page to throw an error.

  * server would not load and threw this error 
  File "/workspace/.pip-modules/lib/python3.8/site-packages/django/template/engine.py", line 52, in __init__
    self.builtins = self.default_builtins + builtins
    self.builtins = self.default_builtins + builtins
TypeError: can only concatenate list (not "set") to list
TypeError: can only concatenate list (not "set") to list

After searching through files I found that in the settings.py file I had added that in templates I had added 'builtins' and its contents using curly brackets instead of square brackets. This resolved the above issue but threw another error.
django.template.library.InvalidTemplateLibrary: Invalid template library specified. ImportError raised when trying to load 'crispy_forms.templatetags.crispy_forms_fields': No module named 'crispy_forms.templatetags.crispy_forms_fields' - I realised I had a spelling error and removed the stray 's' from fields. The server then operated as expected.

* AttributeError: 'Settings' object has no attribute 'STRIPE_PUBLIC_KEY' when I saved the stripe_public_key to my variables in my workspace I had a typo.
* I had forgotten to pip3 install stripe