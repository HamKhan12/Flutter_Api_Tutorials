# Flutter API Integration Tutorial

This project demonstrates two different approaches to handling API data and JSON parsing in Flutter:
1. **Manual Model Creation:** Manually writing the model class and `fromJson` method.
2. **Plugin-Based Model Generation:** Using a code generation plugin to create the model classes automatically.

## Examples Included

### 1. HomeScreen (HomeScreen.dart)
Fetches a list of posts from JSONPlaceholder API and displays them in a list.

- **API Endpoint:** https://jsonplaceholder.typicode.com/posts
- **Model Used:** PostsModel (Generated via plugin using PostsModel.fromJson(i))

### 2. ExampleTwo (ExampleTwo.dart)
Fetches a list of photos from JSONPlaceholder API and displays them with thumbnails and titles.

- **API Endpoint:** https://jsonplaceholder.typicode.com/photos
- **Model Used:** Photos (Manually created within the same file)

## Model Comparison

### Manually Created Model (Photos in ExampleTwo.dart)
```dart
class Photos {
  String title, url;
  int id;

  Photos({required this.title, required this.url, required this.id});
}
// Parsing done manually:
// Photos photos = Photos(title: i['title'], url: i['url'], id: i['id']);
Plugin-Generated Model (PostsModel)
dart
@JsonSerializable()
class PostsModel {
  int? userId;
  int? id;
  String? title;
  String? body;

  PostsModel({this.userId, this.id, this.title, this.body});

  factory PostsModel.fromJson(Map<String, dynamic> json) => 
      _$PostsModelFromJson(json);
  Map<String, dynamic> toJson() => _$PostsModelToJson(this);
}

**##** **Key Concepts Demonstrated**
API Calling: Using http package for GET requests

JSON Parsing: Converting API response to Dart objects

FutureBuilder: Widget that builds based on Future snapshot

State Management: Using setState for local UI state

ListViews: Displaying data in scrollable lists

Model Classes: Structuring API response data

## Packages Used
http: ^1.1.0 - For making HTTP requests

yaml
dependencies:
  http: ^1.1.0
Getting Started
Clone the repository or add files to your project

Add HTTP package to pubspec.yaml and run flutter pub get

For plugin-based models, add dev dependencies:

yaml
dev_dependencies:
  build_runner: ^2.4.0
  json_serializable: ^6.7.0
Run build runner: flutter pub run build_runner build

Run the app and navigate to either screen

## Connect with Me
😊 Follow me on GitHub for more Flutter tutorials and projects:
Your-Github-Username

Replace Your-Github-Username with your actual GitHub username

## Conclusion
This project is excellent for learning networking in Flutter. It shows two practical JSON parsing approaches:

Use Manual Parsing for simplicity and learning fundamentals

Use Code Generation for larger projects with complex JSON structures
