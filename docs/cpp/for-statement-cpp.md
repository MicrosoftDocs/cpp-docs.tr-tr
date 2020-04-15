---
title: for Deyimi (C++)
description: Microsoft Visual Studio C++'daki deyim için Standart C++'a başvuru.
f1_keywords:
- for_cpp
ms.date: 04/14/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: 92f7ae4b1f2fbaaf710cd5a8739b78cb98a0accb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375390"
---
# <a name="for-statement-c"></a>for Deyimi (C++)

Koşul yanlış olana kadar sürekli olarak bir deyimi yürütür. İfade için aralık tabanlı bilgi [için, Deyim için Aralık tabanlı (C++)](../cpp/range-based-for-statement-cpp.md)bakın.

## <a name="syntax"></a>Sözdizimi

> **`for (`***init-expression* **`;`** *cond-expression* **`;`** *döngü-ifade***`)`**\
> &nbsp;&nbsp;&nbsp;&nbsp;_Deyim_**`;`**

## <a name="remarks"></a>Açıklamalar

Belirli sayıda kez yürütülmesi gereken döngüler oluşturmak için **for** deyimini kullanın.

**For** deyimi, aşağıdaki tabloda gösterildiği gibi üç isteğe bağlı bölümden oluşur.

### <a name="for-loop-elements"></a>Döngü Öğeleri için

|Söz Dizimi Adı|Yürütüldüğünde|Açıklama|
|-----------------|-------------------|-----------------|
|`init-expression`|**For** deyiminin başka bir `init-expression` öğesinden önce, yalnızca bir kez yürütülür. Denetim sonra `cond-expression`geçer.|Döngü dizinlerini başlatmak için sık kullanılır. Deyimler ya da bildirimler içerebilir.|
|`cond-expression`|Her yineleme nin yürütülmesinden `statement`önce, ilk yineleme de dahil olmak üzere. `statement`yalnızca doğru `cond-expression` (sıfır olmayan) değerlendirilirse yürütülür.|Tamsayı türüne benzersiz bir dönüştürmesi olan bir integral türünü ya da sınıf türünü değerlendiren deyimdir. Genellikle döngü sonlandırma ölçütünü sınamak için kullanılır.|
|`loop-expression`|Her yinelemenin sonunda `statement`. `loop-expression` Yürütüldükten `cond-expression` sonra değerlendirilir.|Genellikle döngü dizinlerini artırmak için kullanılır.|

Aşağıdaki örnekler, ifade için kullanmak **için** farklı yollar gösterir.

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

`init-expression`ve `loop-expression` virgülle ayrılmış birden çok deyim içerebilir. Örneğin:

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

`loop-expression`artımlı veya kararnameye eklenebilir veya başka şekillerde değiştirilebilir.

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

A **için** döngü, bir [kesme,](../cpp/break-statement-cpp.md) [döndürme](../cpp/return-statement-cpp.md)veya [goto](../cpp/goto-statement-cpp.md) **(for** döngüsü dışında `statement` etiketli bir deyim) yürütüldüğünde sona erer. **For** döngüsündeki [devam](../cpp/continue-statement-cpp.md) deyimi yalnızca geçerli yinelemeyi sonlandırır.

Atlanırsa, `cond-expression` `true`bu kabul edilir , ve **for** döngüsü bir **mola**olmadan sona ermez , **return**, veya içinde `statement` **goto** .

**For** deyiminin üç alanı normalde başlatma, sonlandırma için sınama ve artış için kullanılır, ancak bunlar bu kullanımlarla sınırlı değildir. Örneğin, aşağıdaki kod numaraları 0 ile 4 arasında yazdırır. Bu durumda, `statement` null deyimidir:

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

C++ standardı, **for** döngüsünde bildirilen bir değişkenin **for** döngüsü sona erdikten sonra kapsam dışına gideceğini söyler. Örneğin:

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

Varsayılan olarak, [/Ze](../build/reference/za-ze-disable-language-extensions.md)altında , **for** döngüsünde bildirilen bir **değişken, for** döngüsünün çevreleyen kapsamı sona erene kadar kapsamda kalır.

[/Zc:forScope,](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) döngüler için bildirilen değişkenlerin standart davranışını `/Za`belirtmeye gerek kalmadan sağlar.

Değişkenleri aşağıdaki `/Ze` gibi yeniden bildirmek için **for** döngüsünün kapsam farklarını da kullanmak mümkündür:

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

Bu davranış, **for** döngüsünde bildirilen bir değişkenin standart davranışını daha yakından taklit eder ve döngü bittikten sonra for **döngüsünde** bildirilen değişkenlerin kapsam dışına gitmesini gerektirir. Bir değişken **for** döngüsünde bildirildiğinde, derleyici dahili olarak **döngünün** çevreleyen kapsamında yerel bir değişkene terfi ettirir. Zaten aynı ada sahip yerel bir değişken olsa bile tanıtılırsa.

## <a name="see-also"></a>Ayrıca bkz.

[Yineleme Deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[while Statement (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while Deyimi (C++)](../cpp/do-while-statement-cpp.md)<br/>
[Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)
