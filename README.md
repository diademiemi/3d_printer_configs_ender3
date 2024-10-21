# creality_ender3_sprite_pro_configs
Configurations for my Ender 3 with the Creality Sprite Pro extruder

It was bought as a stock Ender 3, and I've added the following upgrades:
- Creality Sprite Pro extruder
- BLTouch
- Dual Z-axis
- Raspberry Pi 4 with Moonsail
- Klipper firmware
- USB webcam

## Generate PrusaSlicer print configs

I still include these in the repo bcs having an easy history of changes is nice. But you can generate them yourself if you want to change the settings.

The print configs in the PrusaSlicer folder are generated from the `generate.yml` playbook. Why Ansible? Because it's my golden hammer, next question. It takes a base config in `roles/generate_print/templates/` and generates a config for each possible permutation of variables such as speed, toughness and precision. You can then use `./copy-to-prusaslicer.sh` to copy the generated configs to your PrusaSlicer config folder.
Is this the best way to do it? No definitely not, but it works for me and I'm stubborn as fuck and will use Ansible when I can.
```
ansible-playbook generate.yml
```

Also, the playbook is a mess. I definitely could've procedurally generated it, but I was tired and just wanted it to work and don't think anyone is gonna download these anyway!
