# templates
Example of using Mustache templates with Angel.

All you need to do is call a plugin that assigns `app.viewGenerator` to a new function. `mustache` is
the one we will use here.

Views in your `views/` directory will be rendered when `res.render` is called.

```dart
import 'package:angel_common/angel_common.dart';

configureViews(Angel app) async {
  await app.configure(mustache()); // One-line setup
  
  app.get('/', (req, res) => res.render('foo')); // render 'foo.mustache'
  app.get('/bar', (req, res) => res.render('bar', {'baz': 'quux'})); // Render with local data
}
```
