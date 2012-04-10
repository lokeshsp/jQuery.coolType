jQuery.coolType is a highly customizable plugin by [http://www.codetunnel.com Code Tunnel] that makes it easy to write text out character by character.

## Syntax: ##

    coolType(text, [callback], [options])

## Usage: ##

    $(function ()
    {
        $('div').coolType('The meaning of life is 42.');
    });

## Options Usage ##

You can override the default options by manually calling the setup method.

    $(function ()
    {
        $.coolType.setup({ inline: true, style: 'color: red;' });
    });

If you only want to override the default options temporarily then you can pass them in along with the call to the Cool Type function.

    $('div').coolType('Here are some options!', null, { inline: true, style: 'color: red;' })

Cool Type has various options available:

<table>
<tr>
<td><b>option</b></td><td><b>description</b></td>
</tr>
<tr>
<td>speed</td><td>The delay between each letter in milliseconds. The higher the number, the slower it goes. *Default: 25* </td>
</tr>
<tr>
<td>caretChar</td><td>The character to use as the caret when cool typing. *Default: '█'* (character code for a solid block character)</td>
</tr>
<tr>
<td>playSound</td><td>If true coolType will try to play a sound while typing using the sound manager 2 library. You will need to reference and setup sound manager 2 before this option will work. You can download it from http://www.schillmania.com/projects/soundmanager2/ *Default: false*</td>
</tr>
<tr>
<td>soundFile</td><td>The file path for the mp3 you wish to play when playSound is set to true. *Default: empty*</td>
</tr>
<tr>
<td>volume</td><td>Accepts values from 0-100. 100 being the loudest. *Default: 100*</td>
</tr>
<tr>
<td>insertBefore</td><td>A string to insert before the text that is being typed. This can contain HTML if needed. *Default: empty*</td>
</tr>
<tr>
<td>insertAfter</td><td>A string to insert after the text that is being typed. This can contain HTML if needed. *Default: empty*</td>
</tr>
<tr>
<td>delayBefore</td><td>The duration in milliseconds that the caret should pause and blink before typing begins. *Default: 0*</td>
</tr>
<tr>
<td>delayAfter</td><td>The duration in milliseconds that the caret should paush and blink after typing has ended. *Default: 0*</td>
</tr>
<tr>
<td>style</td><td>A string containing CSS styles to be applied to the text being typed. *Default: empty*</td>
</tr>
<tr>
<td>inline</td><td>True if the text should be typed inline in a SPAN tag instead of a block element DIV tag. *Default: false*</td>
</tr>
<tr>
<td>caretBlinkSpeed</td><td>The delay between the caret blinking in milliseconds. The higher the value the slower the blink speed. *Default: 300*</td>
</tr>
</table>

## Callback Usage ##

    $('div').coolType('Here is a callback example.', function (elems)
    {
        alert("Typing has finished!");
    });

## Using Sound ##

jQuery.coolType comes with Sound Manager 2 support built in. Here is the minimum usage required to use Cool Type with sound:

    <script src="/Scripts/jQuery_1.6.2_min.js" type="text/javascript"></script>
    <script src="/Scripts/soundmanager2-nodebug-jsmin.js" type="text/javascript"></script>
    <script src="/Scripts/jQuery.coolType.js" type="text/javascript"></script>
    <script type="text/javascript">
        soundManager.url = //path to .swf files for Sound Manager 2

        $(function ()
        {
            $.coolType.setup(
            {
                playSound: true,
                soundFile: '/fullpath/to/your/sound.mp3',
            });
            
            $('div').coolType('This is a test of the sound support!');
        });
    </script>

## Demonstration ##

For a demonstration of Cool Type in action go to http://www.CodeTunnel.com/projects/CoolType/demo