# trident

1. запустити програму: двічі клікнути на run.bat, почекіти поки запуститься приблизно 20 сек
2. відкрити файл EurotoursSearchPerCountry.url
3. в перше поле ввести початкову дату заселення
4. друге поле це кількість днів проживання, по замовчуванню 7
5. з випадаючого списку вибрати країну по якій будуть генеруватися файли. 
	Країни беруться по наявності з файлу regions.xls і натисніть submit. 
	в консолі буде виводитись інформація про процес, по закінченню буде написано done. 
	це може зайняти трохи часу 30 сек або хвилину. по закінченню можна повторити для іншої країни. 
6. для кожного регіону країни формується запит до євпротурсу, і для кожного готелю створюється окремий файл. Файл зберігається у папку
hotels\{тип поселення}\{назва країни}\{назва регіону}\{назва локації}\{дата заселення}\{назва готелю}

тип поселення  : PP,PPPN,PUPN ... вам потрібен PPPN (per person per night)
дата заселення : якщо на зазначену дату немає готелів для заселення буде перевірятися можливість заселення кожні наступні 7 днів але не більше ніж на 6 тижнів на перед
назва готелю   : назва файлу складається з назви самого готелю(може повторюватися), унікального ідентифікатора готелю та типу поселення PPPN

Обов'язково перевіряйте назву готелю в назві файлу та у самому файлі, 
	також зверніть увагу на заміну німецьких символів (див. файл characterReplace.xls) у назві резортів (локацій), щоб вони співпадали з назвами у вашій базі