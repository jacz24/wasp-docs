# WaspLib Documentation

WaspLib documentation is created in the [WaspLib](https://github.com/WaspScripts/WaspLib) repository 
and you can find the live version here: [](https://waspscripts.github.io/WaspLib/).

This repository is contains the tools and assets used to build the documentation, especially because
the assets are quite bulky.

You can use this on other projects if you want, it builds documentation based on pascal comments in the
source files.

Generates the repository documentation files from comments in the source files and uses markdown.

Example documentation comment:

```markdown
(*
# Mainscreen.PointToMM
```pascal
function TRSMainScreen.PointToMM(MS: TPoint; Height: Int32=0; Accuracy:Double=0.2): Vector3;
```

Takes a mainscreen point and converts it to a point on the minimap.

Returns a Vector3 which includes input height. Conversion to a TPoint if that's what you need is simply
done by calling `.ToPoint()` on the result.

### Example
```pascal
  WriteLn Mainscreen.PointToMM(Point(250,140), 2);
  WriteLn Mainscreen.PointToMM(Point(250,140), 2).ToPoint(); // as a TPoint (lost accuracy)
```
*)
```

You can run this locally with the following commands (Linux):

```bash
cd docgen
sudo apt-get install python3 python3-pip
sudo pip install sphinx furo myst-parser
python3 docgen.py PATH_TO_SOURCE_CODE_ROOT
```