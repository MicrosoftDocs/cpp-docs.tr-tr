---
title: for deyimleri (C++)
description: C++ Microsoft Visual Studio C++ ' daki standart C++ için başvuru.
f1_keywords:
- for_cpp
ms.date: 07/31/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: b32a50e376113f9f9d550d4984d05fc8c675f14d
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520855"
---
# <a name="for-statement-c"></a>`for`ifade (C++)

Koşul yanlış olana kadar sürekli olarak bir deyimi yürütür. Aralık tabanlı bildirimle ilgili bilgi için **`for`** bkz. [Aralık tabanlı `for` ifade (C++)](../cpp/range-based-for-statement-cpp.md).

## <a name="syntax"></a>Syntax

> **`for (`** *`init-expression`* **`;`** *`cond-expression`* **`;`** *`loop-expression`* **`)`**\
> &emsp;*`statement`*

## <a name="remarks"></a>Açıklamalar

**`for`** Belirtilen sayıda yürütülmesi gereken döngüleri oluşturmak için ifadesini kullanın.

**`for`** Bu ifade, aşağıdaki tabloda gösterildiği gibi üç isteğe bağlı bölümden oluşur.

### <a name="for-loop-elements"></a>for döngüsü öğeleri

| Söz dizimi adı | Yürütüldüğünde | Açıklama |
|--|--|--|
| *`init-expression`* | Deyimden başka herhangi bir öğeden önce **`for`** *`init-expression`* yalnızca bir kez yürütülür. Denetimi daha sonra öğesine geçirir *`cond-expression`* . | Döngü dizinlerini başlatmak için sık kullanılır. Deyimler ya da bildirimler içerebilir. |
| *`cond-expression`* | Her yinelemesi yürütmeden önce *`statement`* , ilk yineleme dahil. *`statement`* yalnızca *`cond-expression`* true (sıfır dışında) olarak değerlendirilirse yürütülür. | Tamsayı türüne benzersiz bir dönüştürmesi olan bir integral türünü ya da sınıf türünü değerlendiren deyimdir. Genellikle döngü sonlandırma ölçütünü sınamak için kullanılır. |
| *`loop-expression`* | Her yinelemesinin sonunda *`statement`* . *`loop-expression`* Yürütüldükten sonra *`cond-expression`* değerlendirilir. | Genellikle döngü dizinlerini artırmak için kullanılır. |

Aşağıdaki örneklerde, ifadesini kullanmanın farklı yolları gösterilmektedir **`for`** .

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
    // Output: 01
}
```

*`init-expression`* ve *`loop-expression`* virgülle ayrılmış birden çok deyim içerebilir. Örneğin:

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

*`loop-expression`* arttırılabilmeli veya azaltılır veya başka yollarla değiştirilebilir.

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

**`for`** İçindeki bir döngü, bir [`break`](../cpp/break-statement-cpp.md) , [Return](../cpp/return-statement-cpp.md)veya [`goto`](../cpp/goto-statement-cpp.md) (döngü dışında etiketlenmiş bir ifadeye **`for`** ) yürütüldüğünde sonlandırılır *`statement`* . [`continue`](../cpp/continue-statement-cpp.md)Döngüdeki bir ifade **`for`** yalnızca geçerli yinelemeyi sonlandırır.

*`cond-expression`* Atlanırsa, kabul edilir **`true`** ve **`for`** döngü bir **`break`** , **`return`** veya içinde sonlanmaz **`goto`** *`statement`* .

Deyimin üç alanı **`for`** genellikle başlatma için, sonlandırma için test etmek ve arttırılsa da, bu kullanımlar ile sınırlı değildir. Örneğin, aşağıdaki kod numaraları 0 ile 4 arasında yazdırır. Bu durumda, *`statement`* null deyimidir:

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

## <a name="for-loops-and-the-c-standard"></a>`for`döngüler ve C++ standardı

C++ standardı, bir döngüde bildirildiği bir değişkenin **`for`** döngü bittikten sonra kapsam dışına gidemeyeceğini söyler **`for`** . Örneğin:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

Varsayılan olarak, [/ze](../build/reference/za-ze-disable-language-extensions.md)altında, döngünün **`for`** kapsayan kapsam bitene kadar döngüde belirtilen bir değişken kapsamda kalır **`for`** .

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) , belirtmeye gerek kalmadan döngüler için belirtilen değişkenlerin standart davranışlarını sağlar `/Za` .

Ayrıca, **`for`** aşağıdaki gibi değişkenleri yeniden bildirmek için döngünün kapsam farklarını kullanmak da mümkündür `/Ze` :

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Bu davranış, döngüde belirtilen bir değişkenin standart davranışını daha yakından taklit eder **`for`** . Bu, döngüde belirtilen değişkenlerin döngü yapıldıktan **`for`** sonra kapsam dışına gitmesini gerektirir. Bir değişken bir döngüde bildirildiği zaman **`for`** derleyici, bunu döngünün kapsayan kapsamdaki yerel bir değişkene dahili olarak yükseltir **`for`** . Aynı ada sahip bir yerel değişken zaten mevcut olsa bile yükseltilir.

## <a name="see-also"></a>Ayrıca bkz.

[Yineleme deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[while deyimleri (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while ekstresi (C++)](../cpp/do-while-statement-cpp.md)<br/>
[Aralık tabanlı for deyimleri (C++)](../cpp/range-based-for-statement-cpp.md)
