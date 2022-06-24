Маршруты и обработчики

Что бы добавит маршрут и его обработчик, нужно:
В файле index.php добавить масив в свойсво класса Core, routers.
Массив должен состоять из двух элементов

* Первый элемент - маршрут. Если в маршруте используется динамический параметр, то на его место нужно вписать `:int:`
  таким образом, маршрутизатор поймет, что на этом месте будет число. Пример маршруто снизу
    * `/posts`
    * `/posts/:int:/edit`
* Второй элемент - путь к статическому методу класса, который является обработчиком, контроллером. Пример метода класса
  и его неймспейса
    * `App\Controllers\TagController::show`
    * `App\Controllers\Auth\SignUpController::upload`

  Первый класс файл обработчика находится по такому пути `/src/App/Controllers/`, второй `/src/App/Controllers/Auth`

Пример самого массива

* `["/", "App\Controllers\MainController::index"]`
* `["/tags", "App\Controllers\TagController::index"]`
  
Это значит, что по пути http://example.com/, у нас запустится код, который написан в `App\Controllers\MainController::index`

Так же, если наш маршрут имеет динамические параметры, то они разпарсятася и передадутся в метод класса. 


