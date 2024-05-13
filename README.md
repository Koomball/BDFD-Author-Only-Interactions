# `BDFD` Author Only Interactions
Two methods for author only interactions.

## $authorID in $customID
With this method we will store the `$authorID` inside the buttons customID and use `$onInteraction` <br>
Command:
```
$title[embed]
$addButton[no;button-$authorID;Button;primary]
```
<br>

$onInteraction
```
$textSplit[$customID;-]
$if[$and[$splitText[1]==button;$splitText[2]==$authorID]]
Interaction Code
$endif
```

## $getEmbedData
With this method we will store the `$authorID` in the footer of the embed and use `$onInteraction[button]` this method only allows one button for each interaction but runs faster and looks cleaner. <br>
Command:
```
$title[embed]
$footer[$authorID]
$addButton[no;button;Button;primary]
```
<br>

$onInteraction[button]
```
$if[$getEmbedData[$channelID;$messageID;1;footer]==$authorID]
Interaction Code
$endif
```
