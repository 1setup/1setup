1setup will make a new Mac your own with minimal effort, and it will continue applying all available updates for the OS, apps, homebrew packages, vim plugins etc. 1setup uses [homebrew](http://brew.sh/) for dependency management, [mas](https://github.com/argon/mas) for Mac App Store integration and a curated collection of scripts for OS-specific configurations. 

## How do I install 1setup?

## How do I configure 1setup?

Given a `1setup.yml` file in the local `$HOME/1setup` directory:

```yml
homebrew:
  taps:
    - caskroom/fonts
    - universal-ctags/universal-ctags
  packages:
    - git
    - go
    - universal-ctags
    - vim
  casks:
    - google-chrome
    - iterm2
  fonts:
    - font-meslo-lg-for-powerline
go:
  packages:
    - github.com/tools/godep
    - github.com/rakyll/boom
```

When you run `1setup`, the following will happen:

1. Homebrew taps will be installed first
1. Homebrew packages, casks & fonts will be installed next
1. Go packages will be installed last
1. If any of the above are already installed, 1setup will apply all available updates

## Can I store the `1setup.yml` config file remotely?

Yes, of course. If 1setup does not find `$HOME/1setup/1setup.yml`, it will take your Mac system user and look for `github.com/[YOUR-MAC-SYSTEM-USER]/1setup`.

## How do I tell 1setup about my own dotfiles?

If your dotfiles are already stored on github.com, ensure they are in the `dotfiles` directory, e.g. `github.com/[USER]/dotfiles/dotfiles`, and run `1setup --config https://github.com/[USER]/dotfiles`.
