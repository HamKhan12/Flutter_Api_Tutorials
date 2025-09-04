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

