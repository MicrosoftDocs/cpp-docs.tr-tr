---
title: Alt simge işleci [] | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '[]'
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf12d517647e36c8a0d9428b818f3812bfea2e1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020623"
---
# <a name="subscript-operator-"></a>Alt simge işleci]

## <a name="syntax"></a>Sözdizimi

```
postfix-expression [ expression ]
```

## <a name="remarks"></a>Açıklamalar

Alt simge işleci (de birincil bir ifade olabilir) bir sonek ifadesi **[]**, dizi dizini oluşturma belirtir.

Yönetilen diziler hakkında daha fazla bilgi için bkz. [diziler](../windows/arrays-cpp-component-extensions.md).

Genellikle, tarafından temsil edilen değeri *sonek ifadesi* bir işaretçi değeri, bir dizi tanımlayıcısına gibi ve *ifade* (numaralandırılmış türler dahil) bir tamsayı değeri. Ancak, tüm sözdizimsel olarak olan bir ifadenin bir işaretçi türünde olması ve diğeri Tamsayı türünde olması gereklidir. Tamsayı değeri bu nedenle olabilir *sonek ifadesi* konumu ve işaretçi değeri parantez içinde olabilir *ifade* veya alt simge konumu. Aşağıdaki kod parçasını göz önünde bulundurun:

```cpp
int nArray[5] = { 0, 1, 2, 3, 4 };
cout << nArray[2] << endl;            // prints "2"
cout << 2[nArray] << endl;            // prints "2"
```

Yukarıdaki örnekte, ifade `nArray[2]` aynıdır `2[nArray]`. Neden olan bir alt simge ifadesi sonucu `e1[e2]` tarafından verilen:

`*((e2) + (e1))`

İfade tarafından üretilenleri kaydeder adresi değil *e2* bayt adresinden *e1*. Bunun yerine, adresi dizideki sonraki nesnesini verecek şekilde ölçeklendirilir *e2*. Örneğin:

```cpp
double aDbl[2];
```

Adresleri `aDb[0]` ve `aDb[1]` 8 bayt uzaklıkta olduğu — türünde bir nesnenin boyutunu **çift**. Bu nesne türüne göre ölçeklendirme, C++ dil tarafından otomatik olarak yapılır ve tanımlanan [toplama işleçleri](../cpp/additive-operators-plus-and.md) burada toplama ve çıkarma işlenenden işaretçi türünün ele alınmıştır.

Bir alt simge ifadesinde de aşağıdaki gibi birden fazla alt simge olabilir:

*İfade1* **[** *expression2* **] [** *ifade3* **]** ...

Alt simge ifadeleri soldan sağa ilişkilendirilir. En soldaki alt simge ifadesi *İfade1* **[** *expression2* **]**, ilk olarak değerlendirilir. Eklemesini sonuçları adresi *İfade1* ve *expression2* bir işaretçi ifadesi; forms ardından *ifade3* yeni bir form için bu işaretçi ifadesine eklenir vb. son alt simge ifadesi eklenene dek işaretçi ifadesi. Yöneltme işleci (<strong>\*</strong>) son işaretçi değeri bir dizi türü adresleri sürece son simgeli ifade değerinden sonra uygulanır.

Birden çok alt simgeye sahip ifadeler, çok boyutlu dizilerin öğelerine bakın. Çok boyutlu bir dizi, öğeleri dizi olan bir dizidir. Örneğin, üç boyutlu bir dizinin ilk öğesi iki boyutlu bir dizidir. Aşağıdaki örnek, bildirir ve karakter basit bir iki boyutlu dizi başlatır:

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

Bir dizinin ilk öğesi 0 öğesidir. Bir C++ dizi aralık *dizi*[0] için *dizi*[*boyutu* - 1]. Bununla birlikte, C++, pozitif ve negatif alt simgeler destekler. Negatif alt simgeler dizi sınırları içinde olmalıdır; Aksi takdirde, sonuçlar tahmin edilemez. Aşağıdaki kod, dizi pozitif ve negatif alt simgeler gösterir:

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

Bir 256 adresine işaret ettiğinden negatif indis son satırında bir çalışma zamanı hata oluşturabilecek **int** dizi bellek kaynağı daha düşük konumları. İşaretçi `midArray` Orta kısmındaki başlatılır `intArray`; bu nedenle her iki pozitif ve negatif bir dizi dizinleri üzerinde kullanılacak (ancak tehlikeli) mümkündür. Dizi alt simge hatalara derleme zamanı hatalarına neden olmaz, ancak bunlar tahmin edilmeyen sonuçlara neden.

Alt simge işleci değiştirebilir. Bu nedenle, ifadeleri *dizi*[*dizin*] ve *dizin*[*dizi*] olduğu sürece bir alt simge eşdeğer olmasını garanti edilir İşleç aşırı yüklenmemiş (bkz [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md)). En yaygın kodlama uygulaması ya da çalışır ancak ilk biçimidir.

## <a name="see-also"></a>Ayrıca bkz.

[Son Ek İfadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Diziler](../cpp/arrays-cpp.md)<br/>
[Bir Boyutlu Diziler](../c-language/one-dimensional-arrays.md)<br/>
[Çok Boyutlu Diziler](../c-language/multidimensional-arrays-c.md)<br/>
