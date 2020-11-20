# Parrot

A simple demonstration of the current browsers speech analysis and synthesis capabilities.
The Web Speech API looks very promising to implement a workable voice interface.

This very simple demo *Parrot* can be used as a proof of concept.
To use it, you will need a headset with a microphone.
For now, the demo application has only been tested on Chrome and Windows 10.

![Screenshot](/Parrot.png)

## More voices
It is possible to install more voices by following this procedure: [3]

* Start Powershell as an Administrator
* Execute the following script
>$sourcePath = 'HKLM:\software\Microsoft\Speech_OneCore\Voices\Tokens' #Where the OneCore voices live\
>$destinationPath = 'HKLM:\SOFTWARE\Microsoft\Speech\Voices\Tokens' #For 64-bit apps\
>$listVoices = Get-ChildItem $sourcePath\
>foreach($voice in $listVoices)\
>{\
>$source = $voice.PSPath #Get the path of this voices key\
>copy -Path $source -Destination $destinationPath -Recurse\
>}

## References
The original example was taken from:
<https://wicg.github.io/speech-api/#examples-recognition>
