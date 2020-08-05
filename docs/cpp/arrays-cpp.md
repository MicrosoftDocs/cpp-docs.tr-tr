---
title: Diziler (C++)
ms.date: 08/03/2020
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: cb949f9a17a6b751dae40202bf82e6cb321b526b
ms.sourcegitcommit: 4eda68a0b3c23d8cefa56b7ba11583412459b32f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87565969"
---
# <a name="arrays-c"></a>Diziler (C++)

Dizi, belleğin bitişik bir alanını kaplayan aynı türdeki nesnelerin bir dizisidir. Geleneksel C stili diziler birçok hatanın kaynağıdır, ancak özellikle de daha eski kod tabanlarında ortaktır. Modern C++ ' da, bu bölümde açıklanan C stili diziler yerine [std:: vector](../standard-library/vector-class.md) veya [std:: Array](../standard-library/array-class-stl.md) kullanımını önemle öneririz. Bu standart kitaplık türlerinin her ikisi de öğelerini bitişik bir bellek bloğu olarak depolar. Ancak, çok daha yüksek bir tür güvenliği sağlar ve dizi içinde geçerli bir konuma işaret eden garantili yineleyiciler destekler. Daha fazla bilgi için bkz. [kapsayıcılar (Modern C++)](containers-modern-cpp.md).

## <a name="stack-declarations"></a>Yığın bildirimleri

C++ dizi bildiriminde, dizi boyutu diğer dillerdeki gibi tür adından sonra değil, değişken adından sonra belirtilir. Aşağıdaki örnek, yığın üzerinde ayrılacak bir 1000 Double dizisi bildirir. Öğe sayısı bir tamsayı sabit değeri ya da başka bir sabit ifade olarak sağlanmalıdır. Bunun nedeni derleyicinin ne kadar yığın alanı ayıracağından emin olmak için. çalışma zamanında hesaplanan bir değer kullanamaz. Dizideki her öğeye varsayılan değer olan 0 atanır. Varsayılan değer atamadıysanız, başlangıçta her öğe, bu bellek konumunda olması gereken rastgele değerleri içerir.

```cpp
    constexpr size_t size = 1000;

    // Declare an array of doubles to be allocated on the stack
    double numbers[size] {0};

    // Assign a new value to the first element
    numbers[0] = 1;

    // Assign a value to each subsequent element
    // (numbers[1] is the second element in the array.)
    for (size_t i = 1; i < size; i++)
    {
        numbers[i] = numbers[i-1] * 1.1;
    }

    // Access each element
    for (size_t i = 0; i < size; i++)
    {
        std::cout << numbers[i] << " ";
    }
```

Dizideki ilk öğe, zerıse öğesidir. Son öğe (*n*-1) öğesidir; burada *n* , dizinin içerebileceği öğe sayısıdır. Bildirimdeki öğe sayısı bir integral türünde olmalı ve 0 ' dan büyük olmalıdır. Programınızın bir değeri hiçbir şekilde öğesinden daha büyük bir alt simge işlecine geçirdiğinden emin olmak sizin sorumluluğunuzdadır `(size - 1)` .

Sıfır boyutlu bir dizi yalnızca, bir veya ' deki son alan olduğunda **`struct`** veya **`union`** Microsoft uzantıları etkinleştirildiğinde ( **`/Za`** veya **`/permissive-`** ayarlanmamışsa) geçerlidir.

Yığın tabanlı diziler, yığın tabanlı dizilerden ayırmak ve erişmek için daha hızlıdır. Ancak, yığın alanı sınırlı olur. Dizi öğelerinin sayısı çok fazla yığın belleği kullandığından büyük bir sayı olamaz. Programınıza ne kadar çok şey bağlıdır. Bir dizinin çok büyük olup olmadığını anlamak için profil oluşturma araçlarını kullanabilirsiniz.

## <a name="heap-declarations"></a>Yığın bildirimleri

Yığına ayırmak için çok büyük bir dizi veya derleme zamanında bilinen boyut yok olabilir. Bir ifade kullanarak bu diziyi yığında ayırmak mümkündür [`new[]`](new-operator-cpp.md) . İşleci, ilk öğesine bir işaretçi döndürür. Alt simge işleci, yığın tabanlı bir dizide olduğu gibi işaretçi değişkeni üzerinde de kullanılabilir. İşaretçiyi dizideki herhangi bir rastgele öğeye taşımak için [işaretçi aritmetiğini](../c-language/pointer-arithmetic.md) de kullanabilirsiniz. Şunları sağlamak sizin sorumluluğunuzdadır:

- Artık diziyi ihtiyaç kalmadığında belleği silebilmeniz için özgün işaretçi adresinin bir kopyasını her zaman saklayın.
- işaretçi adresini dizi sınırlarının ötesinde artırmaz veya azalmayın.

Aşağıdaki örnek, çalışma zamanında yığında nasıl dizi tanımlanacağını gösterir. İndis işlecini kullanarak ve işaretçi aritmetiği kullanarak dizi öğelerine nasıl erişebileceğiniz gösterilmektedir:

```cpp

void do_something(size_t size)
{
    // Declare an array of doubles to be allocated on the heap
    double* numbers = new double[size]{ 0 };

    // Assign a new value to the first element
    numbers[0] = 1;

    // Assign a value to each subsequent element
    // (numbers[1] is the second element in the array.)
    for (size_t i = 1; i < size; i++)
    {
        numbers[i] = numbers[i - 1] * 1.1;
    }

    // Access each element with subscript operator
    for (size_t i = 0; i < size; i++)
    {
        std::cout << numbers[i] << " ";
    }

    // Access each element with pointer arithmetic
    // Use a copy of the pointer for iterating
    double* p = numbers;

    for (size_t i = 0; i < size; i++)
    {
        // Dereference the pointer, then increment it
        std::cout << *p++ << " ";
    }

    // Alternate method:
    // Reset p to numbers[0]:
    p = numbers;

    // Use address of pointer to compute bounds.
    // The compiler computes size as the number
    // of elements * (bytes per element).
    while (p < (numbers + size))
    {
        // Dereference the pointer, then increment it
        std::cout << *p++ << " ";
    }

    delete[] numbers; // don't forget to do this!

}
int main()
{
    do_something(108);
}

```

## <a name="initializing-arrays"></a>Dizileri başlatma

Bir dizide, tek seferde bir öğe veya tek bir ifadede bir diziyi başlatabilirsiniz. Aşağıdaki iki dizinin içeriği aynıdır:

```cpp
    int a[10];
    for (int i = 0; i < 10; ++i)
    {
        a[i] = i + 1;
    }

    int b[10]{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
```

## <a name="passing-arrays-to-functions"></a>Dizileri işlevlere geçirme

Bir dizi bir işleve geçirildiğinde, yığın tabanlı veya yığın tabanlı bir dizi olup olmadığı sürece ilk öğeye işaretçi olarak geçirilir. İşaretçi ek boyut veya tür bilgisi içermiyor. Bu davranışa *işaretçi kay*adı verilir. Bir diziyi bir işleve geçirdiğinizde, her zaman öğe sayısını ayrı bir parametrede belirtmeniz gerekir. Bu davranış, Array bir işleve geçirildiğinde dizi öğelerinin kopyalanmadığını da belirtir. İşlevin öğeleri değiştirmesini engellemek için, parametreyi öğe işaretçisi olarak belirtin **`const`** .

Aşağıdaki örnek bir diziyi ve uzunluğu kabul eden bir işlevi gösterir. İşaretçi, kopya değil, orijinal diziyi işaret eder. Parametresi olmadığından **`const`** , işlev dizi öğelerini değiştirebilir.

```cpp
void process(double p*, const size_t len)
{
    std::cout << "process:\n";
    for (size_t i = 0; i < len; ++i)
    {
        // do something with p[i]
    }
}
```

İşlev bloğunda Salt okunabilir hale getirmek için diziyi const olarak bildirin:

```cpp
void process(const double p*, const size_t len);
```

Aynı işlev, davranış değişikliği olmadan bu yollarla da bildirilemez. Dizi, hala ilk öğeye bir işaretçi olarak geçirilir:

```cpp
// Unsized array
void process(const double p[], const size_t len);

// Fixed-size array. Length must still be specified explicitly.
void process(const double p[1000], const size_t len);
```

## <a name="multidimensional-arrays"></a>Çok boyutlu diziler

Diğer dizilerden oluşturulan diziler çok boyutlu dizilerdir. Bu çok boyutlu diziler, sırayla birden çok köşeli parantez içine alınmış sabit ifadeler yerleştirilerek belirtilir. Örneğin, bu bildirimi göz önünde bulundurun:

```cpp
int i2[5][7];
```

Bu **`int`** , aşağıdaki şekilde gösterildiği gibi, kavramsal olarak beş satırlık ve yedi sütundan oluşan iki boyutlu bir matris halinde düzenlenmiş bir türü dizisini belirtir:

![Çoklu&#45;boyutlu bir dizinin kavramsal düzeni](../cpp/media/vc38rc1.gif "Çoklu&#45;boyutlu bir dizinin kavramsal düzeni") <br/>
Çok boyutlu bir dizinin kavramsal düzeni

Başlatıcı listesi olan ( [başlatıcılar](../cpp/initializers.md)bölümünde açıklandığı gibi), çok boyutlu diziler bildirebilirsiniz. Bu bildirimlerde, ilk boyutun sınırlarını belirten sabit ifade atlanabilir. Örnek:

```cpp
// arrays2.cpp
// compile with: /c
const int cMarkets = 4;
// Declare a float that represents the transportation costs.
double TransportCosts[][cMarkets] = {
   { 32.19, 47.29, 31.99, 19.11 },
   { 11.29, 22.49, 33.47, 17.29 },
   { 41.97, 22.09,  9.76, 22.55 }
};
```

Yukarıdaki bildirim, dört sütundan oluşan üç satır olan bir diziyi tanımlar. Satırlar fabrikaları temsil eder ve sütunlar fabrikaların sevk ettiği pazarları temsil eder. Değerler, fabrikaların pazarlarına yönelik taşıma maliyetlerinden alınır. Dizinin ilk boyutu bırakılır, ancak derleyici başlatıcıyı inceleyerek onu doldurur.

N boyutlu dizi türünde yöneltme işlecinin (*) kullanılması n-1 boyutlu bir dizi oluşturur. N 1 ise, bir skaler (veya dizi öğesi) yapılır.

C++ dizileri satır birincil sırada depolanır. Satır ana sıra, son alt simge en hızlı şekilde değişiklik gösterir.

## <a name="example"></a>Örnek

Ayrıca, burada gösterildiği gibi, işlev bildirimlerinde çok boyutlu bir dizinin ilk boyutu için sınır belirtimini atlayabilirsiniz:

```cpp
// multidimensional_arrays.cpp
// compile with: /EHsc
// arguments: 3
#include <limits>   // Includes DBL_MAX
#include <iostream>

const int cMkts = 4, cFacts = 2;

// Declare a float that represents the transportation costs
double TransportCosts[][cMkts] = {
   { 32.19, 47.29, 31.99, 19.11 },
   { 11.29, 22.49, 33.47, 17.29 },
   { 41.97, 22.09,  9.76, 22.55 }
};

// Calculate size of unspecified dimension
const int cFactories = sizeof TransportCosts /
                  sizeof( double[cMkts] );

double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);

using namespace std;

int main( int argc, char *argv[] ) {
   double MinCost;

   if (argv[1] == 0) {
      cout << "You must specify the number of markets." << endl;
      exit(0);
   }
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);
   cout << "The minimum cost to Market " << argv[1] << " is: "
       << MinCost << "\n";
}

double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {
   double MinCost = DBL_MAX;

   for( size_t i = 0; i < cFacts; ++i )
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?
         MinCost : TransportCosts[i][Mkt];

   return MinCost;
}
```

```Output
The minimum cost to Market 3 is: 17.29
```

İşlev, `FindMinToMkt` Yeni fabrikaları eklemek için herhangi bir kod değişikliği gerektirmediğinden, yalnızca bir yeniden derleme gerektirmek üzere yazılır.

## <a name="initializing-arrays"></a>Dizileri Başlatma

Sınıf oluşturucusuna sahip nesne dizileri Oluşturucu tarafından başlatılır. Başlatıcı listesinde dizideki öğelerden daha az öğe olduğunda, kalan öğeler için varsayılan oluşturucu kullanılır. Sınıfı için varsayılan Oluşturucu tanımlanmazsa, başlatıcı listesi *tamamlanmış*olmalıdır, diğer bir deyişle dizideki her öğe için bir başlatıcı olmalıdır.

İki oluşturucu tanımlayan `Point` sınıfını göz önünde bulundurun:

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

İlk `aPoint` öğesi `Point( int, int )` oluşturucusu kullanılarak oluşturulur; kalan iki öğe varsayılan oluşturucu kullanılarak oluşturulur.

Statik üye dizileri ( **`const`** ya da değil) tanımlarında başlatılabilir (sınıf bildiriminin dışında). Örnek:

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```

## <a name="accessing-array-elements"></a>Dizi öğelerine erişme

Dizi alt indis işlecini () kullanarak bir dizinin tek tek öğelerine erişebilirsiniz `[ ]` . Tek boyutlu bir dizinin adını alt simge olmadan kullanırsanız, dizinin ilk öğesine bir işaretçi olarak değerlendirilir.

```cpp
// using_arrays.cpp
int main() {
   char chArray[10];
   char *pch = chArray;   // Evaluates to a pointer to the first element.
   char   ch = chArray[0];   // Evaluates to the value of the first element.
   ch = chArray[3];   // Evaluates to the value of the fourth element.
}
```

Çok boyutlu diziler kullandığınızda ifadelerde çeşitli birleşimler kullanabilirsiniz.

```cpp
// using_arrays_2.cpp
// compile with: /EHsc /W1
#include <iostream>
using namespace std;
int main() {
   double multi[4][4][3];   // Declare the array.
   double (*p2multi)[3];
   double (*p1multi);

   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.
   p2multi = multi[3];               // Make p2multi point to
                                     // fourth "plane" of multi.
   p1multi = multi[3][2];            // Make p1multi point to
                                     // fourth plane, third row
                                     // of multi.
}
```

Yukarıdaki kodda, `multi` türünde üç boyutlu bir dizidir **`double`** . `p2multi`İşaretçi, üç boyutlu bir dizi türüne işaret eder **`double`** . Bu örnekte, dizi bir, iki ve üç alt simge ile kullanılır. Deyimde olduğu gibi tüm alt simgeleri belirtmek daha yaygın olsa da `cout` , bazen izleyen deyimlerde gösterildiği gibi dizi öğelerinin belirli bir alt kümesini seçmek faydalı olur `cout` .

## <a name="overloading-subscript-operator"></a>Alt simge işlecini aşırı yükleme

Diğer işleçler gibi, alt simge işleci ( `[]` ) Kullanıcı tarafından yeniden tanımlanabilir. Alt simge işlecinin varsayılan davranışı, aşırı yüklenmemişse, aşağıdaki yöntemi kullanarak dizi adını ve alt simgeyi birleştirmektir:

`*((array_name) + (subscript))`

İşaretçi türlerini içeren tüm ek bir deyişle, ölçek, türün boyutunu ayarlamak için otomatik olarak yapılır. Sonuç değeri, kaynağından *n* bayt değil `array_name` ; bunun yerine dizinin *n*. öğesidir. Bu dönüştürme hakkında daha fazla bilgi için bkz. [eklenebilir işleçler](additive-operators-plus-and.md).

Benzer şekilde, çok boyutlu diziler için aşağıdaki yöntem kullanılarak adres türetilir:

`((array_name) + (subscript1 * max2 * max3 * ... * maxn) + (subscript2 * max3 * ... * maxn) + ... + subscriptn))`

## <a name="arrays-in-expressions"></a>İfadelerdeki Diziler

Dizi türünün bir tanımlayıcısı **`sizeof`** , bir başvurunun Address-of ( `&` ) veya bir başvurunun başlatılmasından farklı bir ifadede göründüğünde, ilk dizi öğesine bir işaretçiye dönüştürülür. Örnek:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

`psz` işaretçisi `szError1` dizisinin ilk öğesine işaret eder. İşaretçilerden farklı olarak diziler, değiştirilebilir l-Values değildir. Bu nedenle şu atama geçersizdir:

```cpp
szError1 = psz;
```

## <a name="see-also"></a>Ayrıca bkz.

[std:: Array](../standard-library/array-class-stl.md)
