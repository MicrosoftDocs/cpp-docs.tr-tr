---
title: İndis Işleci []
ms.date: 11/04/2016
f1_keywords:
- '[]'
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
ms.openlocfilehash: a4eb878a18aa38b7047104903d10d96d66cc6720
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231097"
---
# <a name="subscript-operator-"></a>İndis Işleci []

## <a name="syntax"></a>Sözdizimi

```
postfix-expression [ expression ]
```

## <a name="remarks"></a>Açıklamalar

Sonek ifadesi (aynı zamanda bir birincil ifade olabilir) ve ardından alt simge işleci ( **[]**), dizi dizinlemeyi belirtir.

C++/CLı ' da yönetilen diziler hakkında daha fazla bilgi için bkz. [diziler](../extensions/arrays-cpp-component-extensions.md).

Genellikle, *sonek ifadesi* tarafından temsil edilen değer, dizi tanımlayıcısı gibi bir işaretçi değeridir ve *ifade* ise tamsayı değerdir (numaralandırılmış türler dahil). Ancak, tüm sözdizimi, ifadelerden birinin işaretçi türü ve diğeri de İntegral türünde olması olabilir. Bu nedenle, tamsayı değeri *sonek ifadesi* konumunda olabilir ve işaretçi değeri *ifade* veya alt simge konumundaki köşeli ayraç içinde olabilir. Aşağıdaki kod parçasını göz önünde bulundurun:

```cpp
int nArray[5] = { 0, 1, 2, 3, 4 };
cout << nArray[2] << endl;            // prints "2"
cout << 2[nArray] << endl;            // prints "2"
```

Yukarıdaki örnekte, ifadesi `nArray[2]` ile aynıdır `2[nArray]` . Bunun nedeni, bir alt simge ifadesinin sonucunun `e1[e2]` tarafından verilme nedenidir:

`*((e2) + (e1))`

İfadenin başvurduğu adres *E1*adresinden *E2* bayt değil. Bunun yerine, adres dizi *E2*sonraki nesneyi verecek şekilde ölçeklendirilir. Örnek:

```cpp
double aDbl[2];
```

Ve adreslerinin her biri, `aDb[0]` `aDb[1]` türünde bir nesnenin boyutu olan 8 bayttır **`double`** . Nesne türüne göre ölçekleme, C++ dili tarafından otomatik olarak yapılır ve işaretçi türü işlenenlerinin eklenmesi ve çıkarılması ele alındığı, ek [işleçlerde](../cpp/additive-operators-plus-and.md) tanımlanmıştır.

Bir alt simge ifadesinde de aşağıdaki gibi birden fazla alt simge olabilir:

*İfade1* **[** *İfade2* **] [** *expression3* **]** ...

Alt simge ifadeleri soldan sağa ilişkilendirilir. En soldaki indis ifadesi, *İfade1* **[** *İfade2* **]**, önce değerlendirilir. *İfade1* ve *Deyim2* ekleme işleminden elde edilen adres bir işaretçi ifadesi; ardından, yeni bir işaretçi ifadesi oluşturmak için bu işaretçi ifadesine *expression3* eklenir ve son alt simge ifadesi eklenene kadar bu şekilde devam eder. Son <strong>\*</strong> simge değeri bir dizi türüne bağlanmadığı müddetçe, son alt indislenmiş ifadeden sonra () yöneltme işleci uygulanır.

Birden çok alt simge içeren ifadeler çok boyutlu dizilerin öğelerine başvurur. Çok boyutlu bir dizi, öğeleri dizi olan bir dizidir. Örneğin, üç boyutlu bir dizinin ilk öğesi iki boyutlu bir dizidir. Aşağıdaki örnek, basit bir iki boyutlu karakter dizisi bildirir ve başlatır:

```cpp
// expre_Subscript_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
#define MAX_ROWS 2
#define MAX_COLS 2

int main() {
  char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };
  for ( int i = 0; i < MAX_ROWS; i++ )
     for ( int j = 0; j < MAX_COLS; j++ )
        cout << c[ i ][ j ] << endl;
}
```

## <a name="positive-and-negative-subscripts"></a>Pozitif ve negatif alt simgeler

Bir dizinin ilk öğesi öğe 0 ' dır. C++ dizisinin aralığı [0] *dizisinden* *diziye*[*size* -1] arasındadır. Ancak, C++ pozitif ve negatif alt simgeleri destekler. Negatif alt simgeler dizi sınırları içine düşmelidir; Aksi takdirde sonuçlar tahmin edilemez. Aşağıdaki kod pozitif ve negatif dizi alt simgeleri gösterir:

```cpp
#include <iostream>
using namespace std;

int main() {
    int intArray[1024];
    for (int i = 0, j = 0; i < 1024; i++)
    {
        intArray[i] = j++;
    }

    cout << intArray[512] << endl;   // 512

    cout << 257[intArray] << endl;   // 257

    int *midArray = &intArray[512];  // pointer to the middle of the array

    cout << midArray[-256] << endl;  // 256

    cout << intArray[-256] << endl;  // unpredictable, may crash
}
```

Son satırdaki negatif alt simge, **`int`** dizinin kaynağından daha düşük bir adres 256 konumuna işaret ettiğinden bir çalışma zamanı hatası oluşturabilir. İşaretçi `midArray` ortasında başlatılır `intArray` ; Bu nedenle, hem pozitif hem de negatif dizi dizinlerini kullanmak mümkündür (ancak tehlikeli). Dizi alt simge hataları derleme zamanı hataları oluşturmaz, ancak öngörülemeyen sonuçlara neden olur.

Alt simge işleci bir işlem olur. Bu nedenle, alt simge işleci aşırı yüklü olmadığı sürece [*Dizin*] ve *Dizin*[*Array*] ifadeleri *dizisi*eşdeğer olarak garanti edilir (bkz. [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md)). İlk form en yaygın kodlama uygulamasıdır, ancak her iki durumda da geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sonek Ifadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Diziler](../cpp/arrays-cpp.md)<br/>
[Tek boyutlu diziler](../c-language/one-dimensional-arrays.md)<br/>
[Çok Boyutlu Diziler](../c-language/multidimensional-arrays-c.md)<br/>
