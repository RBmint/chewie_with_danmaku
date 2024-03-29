# chewie_with_danmaku
A Flutter video player with multiple gesture support, based on Chewie and added danmaku (bullet/barrage) function inside it.

github: https://github.com/RBmint/chewie_with_danmaku

# Description
Everyone loves [chewie], a video player with highly customizable interface. While watching the video,
many would like to see or send a danmaku/bullet/barrage (they are referring to the same thing!), and 
chewie_with_danmaku make everything possible at once, with integrated gesture control to enhance user
experience. 

The danmaku of the player has the following features:

- You can change the color of it
- You can choose its position: flowing on top or fixed at bottom
- You can adjust the display area
- You can adjust the danmaku flowing speed
- You can adjust the display font size

The video player support gestures including:

- Long press the video to play in double speed
- Double tap the video to play/pause video
- Swipe left/right to quickly seek to a desired position
- Swipe up/down in left half of screen to adjust video brightness (based on system brightness) 
- Swipe up/down in right half of screen to adjust video volume (based on system volume)

## Installation
In your pubspec.yaml file within your Flutter Project add [chewie_with_danmaku] under dependencies:
```dart
dependencies:
  chewie_with_danmaku: <latest_version>
```

## Using the player
After adding the dependency in your pubspec.yaml file, you can access the player by simply calling the
widget as below (there are some additional parameters to be explored):

**Please note: you _MUST_ call "createWithDependencies" as some GetX controller need to be created with
this widget to make it functional.**

```dart
import 'package:chewie_with_danmaku/chewie_with_danmaku.dart';
@override
Widget build(BuildContext context) {
  return Scaffold(
    body: Center(
      /// MUST use createWithDependencies
      child: ChewieWithDanmaku.createWithDependencies(
        "https://flutter.github.io/assets-for-api-docs/assets/videos/butterfly.mp4",
        autoPlay: true,
        looping: true,
        aspectRatio: 16 / 9,
        rightButtonList: null,
        videoTitle: "A butterfly demo",
        danmakuList: list,
        primaryColor: Colors.pinkAccent,
      ),
    ),
  );
}
```

The danmaku list is simply a list containing danmaku data, which its content, time and position being
the required fields. Other optional parameters and explanations can be found in danmanku.dart file
```dart
DanmakuData(content: "a initial danmaku", time: 2000, position: 1)
```

## Acknowledgements:
This project is developed based on:
- https://pub.dev/packages/chewie
- https://pub.dev/packages/flutter_danmaku
- https://pub.dev/packages/fplayer

## TODO LIST:
- Add screenshots/preview of the player
- Fix bugs e.g. setState() called during build .etc
- Listen for feedback and add more parameters to the interface
- Learn to write a more detailed documentation
- Add a demo page
