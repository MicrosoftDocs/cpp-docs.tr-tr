---
title: for Deyimi (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: e3dfdb45bdf8a508eca9d29e90b3f7c05e7b147d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179920"
---
# <a name="for-statement-c"></a>for Deyimi (C++)

Koşul yanlış olana kadar sürekli olarak bir deyimi yürütür. Aralık tabanlı for ifadesiyle ilgili bilgi için bkz. [Range-based for deyimin (C++)](../cpp/range-based-for-statement-cpp.md).

## <a name="syntax"></a>Sözdizimi

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>Açıklamalar

Belirli sayıda yürütülmesi gereken döngüler oluşturmak için **for** ifadesini kullanın.

**For** deyimleri, aşağıdaki tabloda gösterildiği gibi üç isteğe bağlı bölümden oluşur.

### <a name="for-loop-elements"></a>Döngü Öğeleri için

|Söz Dizimi Adı|Yürütüldüğünde|Açıklama|
|-----------------|-------------------|-----------------|
|`init-expression`|**For** deyimindeki diğer öğeden önce `init-expression` yalnızca bir kez yürütülür. Denetim daha sonra `cond-expression`geçirir.|Döngü dizinlerini başlatmak için sık kullanılır. Deyimler ya da bildirimler içerebilir.|
|`cond-expression`|Her bir `statement`yinelemesi yürütmeden önce, ilk yineleme dahil. `statement`, yalnızca `cond-expression` true (sıfır dışında) olarak değerlendirilirse yürütülür.|Tamsayı türüne benzersiz bir dönüştürmesi olan bir integral türünü ya da sınıf türünü değerlendiren deyimdir. Genellikle döngü sonlandırma ölçütünü sınamak için kullanılır.|
|`loop-expression`|Her `statement`yinelemesi sonunda. `loop-expression` yürütüldükten sonra, `cond-expression` değerlendirilir.|Genellikle döngü dizinlerini artırmak için kullanılır.|

Aşağıdaki örneklerde **for** ifadesini kullanmanın farklı yolları gösterilmektedir.

```cpp
#include <iostream>
using namespace std;

int main() {
    // The counter variable can be declared in the init-expression.
    for (int i = 0; i < 2; i++ ){
       cout << i;
    }
    // Output: 01
    // The counter variable can be declared outside the for loop.
    int i;
    for (i = 0; i < 2; i++){
        cout << i;
    }
    // Output: 01
    // These for loops are the equivalent of a while loop.
    i = 0;
    while (i < 2){
        cout << i++;
    }
}
    // Output: 012
```

`init-expression` ve `loop-expression`, virgülle ayrılmış birden çok deyim içerebilir. Örneğin:

```cpp
#include <iostream>
using namespace std;

int main(){
    int i, j;
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {
        cout << "i + j = " << (i + j) << '\n';
    }
}
    // Output:
    i + j = 15
    i + j = 17
    i + j = 19
```

`loop-expression` arttırılabilmeli veya azaltılır ya da başka yollarla değiştirilebilir.

```cpp
#include <iostream>
using namespace std;

int main(){
for (int i = 10; i > 0; i--) {
        cout << i << ' ';
    }
    // Output: 10 9 8 7 6 5 4 3 2 1
    for (int i = 10; i < 20; i = i+2) {
        cout << i << ' ';
    }
    // Output: 10 12 14 16 18
```

`statement` içinde bir [Break](../cpp/break-statement-cpp.md), [Return](../cpp/return-statement-cpp.md)veya [goto](../cpp/goto-statement-cpp.md) ( **for** döngüsünün dışında) yürütüldüğünde bir **for** döngüsü sonlandırılır. **For** döngüsünde [Continue](../cpp/continue-statement-cpp.md) deyimleri yalnızca geçerli yinelemeyi sonlandırır.

`cond-expression` atlanırsa, true olarak değerlendirilir ve **for** döngüsü, `statement`içinde **Break**, **Return**veya **goto** olmadan sonlandırılmaz.

**For** ifadesinin üç alanı genellikle başlatma için, sonlandırma için test etmek ve arttırılsa da bu kullanımları sınırlandırılmazlar. Örneğin, aşağıdaki kod numaraları 0 ile 4 arasında yazdırır. Bu durumda, `statement` null deyimidir:

```cpp
#include <iostream>
using namespace std;

int main()
{
    int i;
    for( i = 0; i < 5; cout << i << '\n', i++){
        ;
    }
}
```

## <a name="for-loops-and-the-c-standard"></a>Döngüler ve C++ Standartı için

Standart C++ , **for döngüsünde bildirildiği** bir değişkenin **for** döngüsü bittikten sonra kapsam dışına gidemeyeceğini söyler. Örneğin:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

Varsayılan olarak, [/ze](../build/reference/za-ze-disable-language-extensions.md)altında **, for döngüsünün** kapsayan kapsamı bitene kadar **for** döngüsünde belirtilen bir değişken kapsamda kalır.

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) , `/Za`belirtmeye gerek kalmadan döngüler için belirtilen değişkenlerin standart davranışlarını sağlar.

Ayrıca, **for** döngüsünün kapsam farklılıklarını, `/Ze` altındaki değişkenleri aşağıdaki gibi yeniden bildirmek üzere kullanmak da mümkündür:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Bu, **for döngüsünde belirtilen** bir değişkenin standart davranışını daha yakından taklit eder. bu **, for döngüsünde** belirtilen değişkenlerin döngü yapıldıktan sonra kapsam dışına gitmesini gerektirir. Bir değişken bir **for** döngüsünde bildirildiği zaman, derleyici, aynı ada sahip bir yerel değişken zaten olsa bile, kendisini **for** döngüsünün kapsayan kapsamındaki yerel bir değişkene yükseltir.

## <a name="see-also"></a>Ayrıca bkz.

[Yineleme Deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[while Deyimi (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while Deyimi (C++)](../cpp/do-while-statement-cpp.md)<br/>
[Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)
