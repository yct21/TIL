Never write your own receive loop in GenServer or OTP
========

> You should never call "receive" from inside a GenServer or an Agent. That's because they already have their own receive loop that handles a lot of different messages, including system ones, code change and what not. Once you call your own "receive", your loop does not know how to handle any of those messages, so you end-up crippling your GenServer / Agent implementations.

## Reference

- [google group - elixir lang talk](https://groups.google.com/forum/#!topic/elixir-lang-talk/SbwY23ORz3A)
