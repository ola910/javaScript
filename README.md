// Select color input
// Select size input
var height,width,color;

// When size is submitted by the user, call makeGrid()
$('#sizePicker').submit(function (pixel) {
    pixel.preventDefault();
    height=$('#inputHeight').val();
    width=$('#inputWidth').val();
    makeGrid(height,width);
    console.log('height: ' + height + ' and width: ' + width);
})

function makeGrid(o, d) {
    $('tr').remove();

    // Your code goes here!

    for (var x = 1; x <= o; x++) {
        $('#pixelCanvas').append('<tr id=table' + x + '></tr>');
        for (var y = 1; y <= d; y++){
            $('#table' + x).append('<td></td>');
        }
    }

    //add color to cell

    $('td').click(function addColor(){
        color = $('#colorPicker').val();
        if ($(this).attr('style')) {
            $(this).removeAttr('style')
        } else{
            $(this).attr('style', 'background-color:' + color);
        }
    })
}
