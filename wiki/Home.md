# Home




```shell
function resize {
    local input_file=$1
    local dim_x=$2
    local dim_y=$3
    local output_file=${input_file/\..*/}_${dim_x}x${dim_y}.jpg
    local gravity=${4:-center} # cardinal directions: north, south, east, west, northeast, southeast, southwest, northwest, center

    convert $input_file -resize ${dim_x}x${dim_y}^ -gravity ${gravity} -extent ${dim_x}x${dim_y} $output_file
}
```