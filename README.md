# otype

OpenType for Oberon for [polpo](https://github.com/polpo-system/polpo): reading TrueType and
OpenType font files (`OType`), the interpreter of their hinting instructions (`OTInt`,
`OTScan`), and Oberon raster fonts made from them (`OTFonts`). Gfx uses it through the package
gfx-otype.

```
portia.Install otype
```

## Using

    OTFonts.Make Arialb.TTF Arial b 10 12 14 Scn Pr3 ~   Oberon raster fonts Arial10b.Scn.Fnt
                                                          and so on from a TrueType font file
    OTFonts.Install       fonts made from OpenType files when they are asked for

`share/OType.Text` is the documentation (from Linux Oberon; its installation chapter is about
the old archive, portia does that now).

## What is here

    src/OTInt.Mod, OTScan.Mod     the interpreter of the hinting instructions
    src/OType.Mod                 the font files
    src/OTFonts.Mod               Oberon fonts from them
    share/OType.Text
    tools/OType.Tool
    test/OTypeTest.Mod

The package has no TrueType font of its own; the test only loads the modules. The sources come from ETH Linux Oberon (OLR, 2017-06-18), converted from Oberon texts to plain
text; the first commit has them unchanged. They compile unchanged with all five of polpo's compilers
(x86, ARM, ARMv7, RISC-V, MIPS).

## Tests

    OTypeTest.Run      2 checks: OType and OTFonts loaded; it needs the desktop's display

The license is GPL-3 (`LICENSE`); the code comes from ETH Oberon, whose license (`LICENSE.ETH`)
asks to keep its copyright notice and conditions, which `LICENSE.ETH` does.
