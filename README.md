# GCODE Path Extender

I added a drag knife to my 3D Printer to cut vinyl. Since drag knife blades are off centered, it would leave my cut with gaps.

I wrote this to extend the paths of the GCODE generated by LaserWeb.

## Installation
`npm install -g gcode-path-extender`

## Usage

`gcode-path-extender [options] <input file> [output file]`

Options:

    -V, --version                 output the version number
    -t, --tool-off-gcode [gcode]  Tool Off GCODE (default: G1 Z3)
    -e, --extend [millimeters]    Extend each path by how many millimeters (default: 4)
    -h, --help                    output usage information

## Example

* Extend each path in `cube.gcode` by 6mm and save it to `cube-extended.gcode`

  `gcode-path-extender --extend 6 cube.gcode cube-extended.gcode`


* Extend each path in `cube.gcode` by 6mm and output to stdout

  `gcode-path-extender --extend 6 cube.gcode`

* Extend each path in `cube.gcode` by 4mm (default) and output to stdout. The GCODE for tool off is `G1 Z4`

  `gcode-path-extender --tool-off-gcode 'G1 Z4' cube.gcode`

## Proof

I uploaded sample files [bathtub.gcode](https://raw.githubusercontent.com/vietquocnguyen/gcode-path-extender/master/sample_files/bath-tub.gcode) and [bathtub-extended](https://raw.githubusercontent.com/vietquocnguyen/gcode-path-extender/master/sample_files/bath-tub-extended.gcode) so you can visualize the difference in a GCODE Viewer like http://jherrm.com/gcode-viewer/.