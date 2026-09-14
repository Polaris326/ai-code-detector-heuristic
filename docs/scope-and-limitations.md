# Scope and Limitations

This module is intended for transparent, client-side code review experiments. It analyzes a source string against configured regular-expression rules and returns the matching evidence.

It does not call an AI model, inspect a remote repository, compare code against a corpus, or determine who authored code. A match means only that a configured style signal was present. A non-match does not prove that code was written without AI assistance.

The accompanying browser tool processes pasted or selected source in the browser. Its current interface supports Python, JavaScript, Java, C++, PHP, and C# inputs. This standalone module itself receives a string and can be adapted to another source format by supplying a different rule set.

For the live local-processing interface, visit [ismycodeai.com](https://ismycodeai.com/).
