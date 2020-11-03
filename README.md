# flutter_admin_scaffold

A scaffold class with a sidebar.

<img width=720 src="example.gif">

## Usage

```dart
import 'package:flutter_admin_scaffold/flutter_admin_scaffold.dart';
import 'package:flutter_admin_scaffold/menu_item_data.dart';
import 'package:flutter_admin_scaffold/sidebar.dart';
```

You can add a sidebar as shown below. See `example` for details.

```dart
class DashboardPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return AdminScaffold(
      appBar: AppBar(
        title: const Text('Sample'),
      ),
      sidebar: Sidebar(
        itemDatas: const [
          MenuItemData(
            title: 'Dashboard',
            route: '/',
            icon: Icons.dashboard,
          ),
          MenuItemData(
            title: 'Top Level',
            icon: Icons.file_copy,
            children: [
              MenuItemData(
                title: 'Second Level Item 1',
                route: '/secondLevelItem1',
              ),
              MenuItemData(
                title: 'Second Level Item 2',
                route: '/secondLevelItem2',
              ),
              MenuItemData(
                title: 'Third Level',
                children: [
                  MenuItemData(
                    title: 'Third Level Item 1',
                    route: '/thirdLevelItem1',
                  ),
                  MenuItemData(
                    title: 'Third Level Item 2',
                    route: '/thirdLevelItem2',
                  ),
                ],
              ),
            ],
          ),
        ],
        selectedRoute: route,
        onSelected: (itemData) {
          Navigator.of(context).pushNamed(itemData.route);
        },
      ),
      body: Container(
        alignment: Alignment.topLeft,
        padding: const EdgeInsets.all(10),
        child: Text(
          'Dashboard',
          style: TextStyle(
            fontWeight: FontWeight.w700,
            fontSize: 36,
          ),
        ),
      ),
    );
  }
}
```
