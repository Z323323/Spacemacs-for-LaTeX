# Spacemacs for FREE LaTeX documentation production

This is the complete introduction to install and use Spacemacs for FREE LaTeX documentation production in an Ubuntu environment.

![Spacemacs](./Spacemacs.png)

Let's get to the point as quick as possible.

## Install TeX Live

The very first thing you'll ~always have to do if you want to create LaTeX projects on your computer is to download the enigmatic ```texlive-full``` through
```bash
sudo apt-get install texlive-full
```
Don't get me wrong, you could still achieve some working solution without downloading ~7GB data package, but, if you don't want to always worry about lacking dependencies you should definitely install it. Now, if you have Ubuntu (I have 22.04 LTS and STILL, after many years, this "bug" is present) you'll probably face the cursed ```Pregenerating ConTeXt MarkIV format. This may take some time...```. If your installation goes fine then you won't have to solve. If not, then ```This may take some time...``` means ```This may take some eternities...```. Now, for some arcane reason you'll have to keep your ```ENTER``` button pushed down until it solves. There's been someone in the past who probably destroyed his keyboard doing this and solving by brute force.

![MarkIVBugFix1](./MarkIVFormatBugFix1.png)
![MarkIVBugFix2](./MarkIVFormatBugFix2.png)

## "Install" Spacemacs

Spacemacs is not really a program on its behalf; it's more like a infinite-power-up-customization of the great old Emacs. Since EVERY Ubuntu distro, up to 2025, has it preinstalled you might guess you'll just need to install Spacemacs config file through
```bash
git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
```
and run ```emacs``` (because ```emacs``` reads the config file at the directory shown above at runtime and "behaves accordingly"). Indeed, this won't be enough ;'''D (but you still have to run the previous command and clone the repo ofc). The problem is that the last version of Spacemacs requires Emacs v28.2, and Ubuntu 22 LTS has v27.1 installed. If you use ```apt-get``` you won't get the desired outcome, because ```apt-get``` only downloads very stable versions, and v28.2 is not recognised as one.

Now, I SUGGEST to install the version 30.2 through
```bash
sudo snap install emacs --classic
```
Please, don't make the same error I made and think this will install the stable version of Emacs stopping the process, just let it download, otherwise it will be painful to solve.

Alright, now you have v30.2>v28.2 which should be fine (it is). Now, if you run ```emacs``` you (guess what) won't get the desired outcome because the ```emacs``` version you downloaded is located at ```/snap/bin/emacs```, while the other version is located at ```/usr/bin/emacs``` and overrides the new version. In order to be able to solve this problem permanently, you'll have to head to ```~/.bashrc``` if you use ```bash```, or to ```~/.zshrc``` if you use ```zsh``` or **OhMyZsh** like I do. Now, edit the file with ```nano``` or whatever you use to edit files and put the following line into it
```bash
alias emacs='/snap/bin/emacs'
```
then save, and run ```source ~/.bashrc``` or ```source ~/.zshrc``` to reload. This will redirect the ```emacs``` command to the right binary. Now, finally, run ```emacs```, and you'll be projected into the Space(macs). Set a couple of configurations (trivial, I suggest Vim [evil] mode) and let Spacemacs download some planets.

### How it should be done for OhMyZsh

Heading to the very end of ```~/.zshrc```, you'll see there's a clear note on how it should be made.

![OhMyZshNote](OhMyZshNote.png)

Now, if you take a look at ```env```, you'll realize ```$ZSH_CUSTOM``` hasn't really been set. I'm not sure how this works, but it simple in this case to imagine that **OhMyZsh** software take a look at alises define at ```$ZSH/custom/aliases.zsh```. Heading to ```~/.oh-my-zsh/custom``` folder you can see there's not a file named ```aliases.zsh```, then, we simply create it through
```bash
echo "alias emacs='/snap/bin/emacs'" > aliases.zsh
```
obtaining a clean modification. Now run ```emacs``` or (if it doesn't work) quit terminal then run ```emacs``` and you should be projected into the Space.

## Configure Spacemacs to be able to use LaTeX

Spacemacs allows to do infinite many things with files and things I can't even imagine. Since it's an OG software it has been created to be used without the help of the cursor. **Every single function you use is addressed by some keystroke.** This creates some misunderstandings at first, take your time. Once you are comfortable, press the sequence ```SPC f e d``` [ ```SPC``` = spacebar ] to open the Spacemacs configuration file through the Spacemacs interface. Navigate through the file and insert ```latex``` inside the ```dotspacemacs-configuration-layers``` section, like this
```bash
(setq dotspacemacs-configuration-layers
  '(
    ;; ... other layers
    latex
    ;; ...
  ))
```
(to insert text you'll have to press ```i```, insert text, then press ```esc``` [ the button ``ESC`` ]). Now save the file with ```SPC f s```, then, reload the configuration with ```SPC f e R```. This last command will make Spacemacs download the LaTeX package. Rerunning ```SPC f e d``` you should see this output

![SpacemacsDotFile](SpacemacsDotFile.png)


