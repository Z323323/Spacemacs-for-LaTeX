# Spacemacs for FREE LaTeX documentation production

This is the complete introduction to install and use Spacemacs for FREE LaTeX documentation production in an Ubuntu environment.

Overleaf platform has privatized LaTeX documentation production through the use of their service. Don't get me wrong, I have NOTHING against Overleaf team, since Overleaf is a GREAT service and it's fair to pretend a payment based on its usage. BUT, LaTeX has been created as an open source project FOR HUMANITY, and so, THERE MUST BE A WAY TO GENERATE SCIENTIFIC DOCUMENTATION FOR FREE. Print this last statement on your soul please.

Fortunately, this is still possible thanks to Spacemacs and its awesome team of community mainteiners. 

![Spacemacs](./Spacemacs.png)

Let's get to the point as quick as possible.

## "Install" Spacemacs

Spacemacs is not really a program on its behalf; it's more like a power-up-customization of the great old Emacs. Since EVERY Ubuntu distro, up to $2025$, has it preinstalled you might guess you'll just need to install Spacemacs config file. Indeed, this is not the way ;'''D. The problem is that the last version of Spacemacs requires Emacs v.28.1, and Ubuntu 22 LTS has v27.1 installed. Thus, if you use ```apt-get``` you won't get the desired outcome.

Now, I SUGGEST to install the version 30.2 through
```bash
sudo snap install emacs --classic
```
Please, don't make the same error I made and think this will install the stable version of Emacs stopping the process, just let it download.

Beautiful, now you have v.30.2>28.1 which should be fine (it is). Now, if you run ```emacs``` you (guess what) won't get the desired outcome because the ```emacs``` version you downloaded is located in ```
