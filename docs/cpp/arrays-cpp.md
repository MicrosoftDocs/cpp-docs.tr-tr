---
title: Diziler (C++)
ms.date: 11/14/2019
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: 91c57a9c4ef190dcace1813dd81739ac72e6b358
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188998"
---
# <a name="arrays-c"></a>Diziler (C++)

Dizi, belleğin bitişik bir alanını kaplayan aynı türdeki nesnelerin bir dizisidir. Geleneksel C stili diziler birçok hatanın kaynağıdır, ancak özellikle de daha eski kod tabanlarında ortaktır. Modern C++sürümünde, bu bölümde açıklanan C stili diziler yerine [std:: vector](../standard-library/vector-class.md) veya [std:: Array](../standard-library/array-class-stl.md) kullanımını önemle öneririz. Bu standart kitaplık türlerinin her ikisi de öğelerini bitişik bir bellek bloğu olarak depolar, ancak dizi içinde geçerli bir konuma işaret eden yineleyiciler ile çok daha yüksek tür güvenliği sağlar. Daha fazla bilgi için bkz. [kapsayıcılar ( C++modern)](containers-modern-cpp.md).

## <a name="stack-declarations"></a>Yığın bildirimleri

C++ Dizi bildiriminde, dizi boyutu diğer dillerdeki tür adından sonra değil, değişken adından sonra belirtilir. Aşağıdaki örnek, yığın üzerinde ayrılacak bir 1000 Double dizisi bildirir. Derleyicinin ne kadar yığın alanı ayıracağından emin olması gerektiğinden, öğelerin sayısı bir tamsayı sabit değeri veya başka bir sabit ifade olarak sağlanmalıdır; çalışma zamanında hesaplanan bir değer kullanamaz. Dizideki her öğeye varsayılan değer olan 0 atanır. Varsayılan bir değer atamadıysanız, her bir öğe başlangıçta bu konumda olacak şekilde hangi rastgele değerlerin olacağını içerecektir.

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

Dizideki ilk öğe 0TH öğesidir ve son öğe (*n*-1) öğesidir; burada *n* , dizinin içerebileceği öğelerin sayısıdır. Bildirimdeki öğe sayısı bir integral türünde olmalı ve 0 ' dan büyük olmalıdır. Programınızın `(size - 1)`değerinden büyük bir değeri hiç bir değer alt simge işlecine geçirmemesini sağlamak sizin sorumluluğunuzdadır.

Sıfır boyutlu bir dizi yalnızca dizi bir **yapıda** veya **birleşimde** son alan olduğunda ve Microsoft uzantıları (/Ze) etkin olduğunda geçerlidir.

Yığın tabanlı diziler, yığın tabanlı dizilere göre ayrılmak ve erişim için daha hızlıdır, ancak öğe sayısı çok fazla yığın belleği kullandığından büyük bir sayı olamaz. Programınıza ne kadar çok şey bağlıdır. Bir dizinin çok büyük olup olmadığını anlamak için profil oluşturma araçlarını kullanabilirsiniz.

## <a name="heap-declarations"></a>Yığın bildirimleri

Yığında ayrılabilecek çok büyük bir dizi olması veya boyutunun derleme sırasında tanınabilmesi durumunda, bunu yığın üzerinde [Yeni bir\[\]](new-operator-cpp.md) ifadesiyle ayırabilirsiniz. İşleci, ilk öğesine bir işaretçi döndürür. Yalnızca yığın tabanlı bir dizi gibi işaretçi değişkeni ile birlikte indis işlecini kullanabilirsiniz. İşaretçiyi dizideki herhangi bir rastgele öğeye taşımak için [işaretçi aritmetiğini](../c-language/pointer-arithmetic.md) de kullanabilirsiniz. Şunları sağlamak sizin sorumluluğunuzdadır:

- Artık diziyi ihtiyaç kalmadığında belleği silebilmeniz için özgün işaretçi adresinin bir kopyasını her zaman saklayın.
- dizi sınırlarının ötesinde işaretçi adresini artırmaz veya azalmayın.

Aşağıdaki örnek, çalışma zamanında yığında bir dizinin nasıl tanımlanacağını ve indis işleci kullanılarak veya işaretçi aritmetiği kullanılarak dizi öğelerine nasıl erişecağınızı gösterir:

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

Bir dizi bir işleve geçirildiğinde, ilk öğeye işaretçi olarak geçirilir. Bu, hem yığın tabanlı hem de yığın tabanlı diziler için geçerlidir. İşaretçi ek boyut veya tür bilgisi içermiyor. Bu davranışa *işaretçi kay*adı verilir. Bir diziyi bir işleve geçirdiğinizde, her zaman öğe sayısını ayrı bir parametrede belirtmeniz gerekir. Bu davranış, Array bir işleve geçirildiğinde dizi öğelerinin kopyalanmadığını da belirtir. İşlevin öğeleri değiştirmesini engellemek için parametreyi **const** öğelerine yönelik bir işaretçi olarak belirtin.

Aşağıdaki örnek bir diziyi ve uzunluğu kabul eden bir işlevi gösterir. İşaretçi, kopya değil, orijinal diziyi işaret eder. Parametre **const**olmadığından, işlev dizi öğelerini değiştirebilir.

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
void process(const double p[] const size_t len);

// Fixed-size array. Length must still be specified explicitly.
void process(const double p[1000], const size_t len);
```

## <a name="multidimensional-arrays"></a>Çok boyutlu diziler

Diğer dizilerden oluşturulan diziler çok boyutlu dizilerdir. Bu çok boyutlu diziler, sırayla birden çok köşeli parantez içine alınmış sabit ifadeler yerleştirilerek belirtilir. Örneğin, bu bildirimi göz önünde bulundurun:

```cpp
int i2[5][7];
```

Bu, aşağıdaki şekilde gösterildiği gibi, kavramsal olarak, beş satır ve yedi sütun şeklinde iki boyutlu bir matris halinde düzenlenmiş, **int**türünde bir diziyi belirtir:

![Çok&#45;boyutlu bir dizinin kavramsal düzeni](../cpp/media/vc38rc1.gif "Çok&#45;boyutlu bir dizinin kavramsal düzeni") <br/>
Çok boyutlu bir dizinin kavramsal düzeni

Başlatıcı listesi olan çok boyutlu dizilerin bildirimlerinde ( [başlatıcılarda](../cpp/initializers.md)açıklandığı gibi), ilk boyutun sınırlarını belirten sabit ifade atlanabilir. Örneğin:

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

N boyutlu dizi türünde yöneltme işlecinin (*) kullanılması n-1 boyutlu bir dizi oluşturur. {1&gt;n&lt;1} 1 ise, skaler (veya dizi öğesi) oluşturulur.

C++diziler satır birincil sırada depolanır. Satır ana sıra, son alt simge en hızlı şekilde değişiklik gösterir.

## <a name="example"></a>Örnek

Çok boyutlu bir dizinin ilk boyutu için sınır belirtimini atlama tekniği, işlev bildirimlerinde aşağıdaki gibi de kullanılabilir:

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

`FindMinToMkt` işlevi, yeni fabrikaları eklemek için herhangi bir kod değişikliği gerektirmediğinden, yalnızca bir yeniden derleme gerektirirken yazılır.

## <a name="initializing-arrays"></a>Dizileri Başlatma

Bir sınıfın oluşturucusu varsa, bu sınıfın dizileri oluşturucu tarafından başlatılır. Başlatıcıda dizideki öğelerden daha az öğe varsa, kalan öğeler için varsayılan oluşturucu kullanılır. Sınıf için varsayılan oluşturucu tanımlanmamışsa, başlatıcı listesi eksiksiz olmalı, yani dizideki her öğe için bir başlatıcı olmalıdır.

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

Statik üye dizileri ( **const** veya Not) tanımlarında başlatılabilir (sınıf bildirimi dışında). Örneğin:

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

Dizi alt simge işlecini (`[ ]`) kullanarak bir dizinin tek tek öğelerine erişebilirsiniz. Tek boyutlu bir dizi, alt simge içermeyen bir ifadede kullanılırsa, dizi adı dizideki ilk öğe için bir işaretçi olarak değerlendirilir.

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

Yukarıdaki kodda `multi` **Double**türünde üç boyutlu bir dizidir. `p2multi` işaretçisi, üç boyutlu **iki** tür dizisine işaret eder. Bu örnekte, dizi bir, iki ve üç alt simge ile kullanılır. `cout` deyiminde olduğu gibi tüm alt simgeleri belirtmek için daha yaygın olsa da, `cout`izleyen deyimlerde gösterildiği gibi bazen dizi öğelerinin belirli bir alt kümesini seçmek faydalı olur.

## <a name="overloading-subscript-operator"></a>Alt simge işlecini aşırı yükleme

Diğer işleçler gibi, alt simge işleci (`[]`) Kullanıcı tarafından yeniden tanımlanabilir. Alt simge işlecinin varsayılan davranışı, aşırı yüklenmemişse, aşağıdaki yöntemi kullanarak dizi adını ve alt simgeyi birleştirmektir:

`*((array_name) + (subscript))`

İşaretçi türleri içeren tüm toplama işlemlerinde olduğu gibi; ölçeklendirme, tür boyutunu ayarlamak için otomatik olarak gerçekleştirilir. Bu nedenle, sonuç değeri dizi adı kaynağından *n* bayt değil; Bunun yerine, dizinin *n*. öğesidir. Bu dönüştürme hakkında daha fazla bilgi için bkz. [eklenebilir işleçler](additive-operators-plus-and.md).

Benzer şekilde, çok boyutlu diziler için aşağıdaki yöntem kullanılarak adres türetilir:

`((array_name) + (subscript1 * max2 * max3 * ... * maxn) + (subscript2 * max3 * ... * maxn) + ... + subscriptn))`

## <a name="arrays-in-expressions"></a>İfadelerdeki Diziler

Dizi türünün bir tanımlayıcısı `sizeof`, adres-of (`&`) veya bir başvurunun başlatılmasından farklı bir ifadede göründüğünde, ilk dizi öğesine bir işaretçiye dönüştürülür. Örneğin:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

`psz` işaretçisi `szError1` dizisinin ilk öğesine işaret eder. İşaretçilerin aksine diziler, değiştirilebilir l-Values değildir. Bu nedenle aşağıdaki atama geçersizdir:

```cpp
szError1 = psz;
```

## <a name="see-also"></a>Ayrıca bkz.

[std:: Array](../standard-library/array-class-stl.md)
