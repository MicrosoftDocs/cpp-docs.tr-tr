---
description: 'Daha fazla bilgi edinin: algoritmalar'
title: Algoritmalar
ms.date: 10/18/2018
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
ms.openlocfilehash: 9d270b35720211c099876eb899e4ef5add9813cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163762"
---
# <a name="algorithms"></a>Algoritmalar

Algoritmalar, C++ standart kitaplığının temel bir parçasıdır. Algoritmalar, kapsayıcılarla, ancak yineleyiciler ile çalışmaz. Bu nedenle, C++ standart kitaplık kapsayıcılarının hepsi olmadığı için aynı algoritma çok fazla kullanılabilir. Bu bölümde, C++ standart kitaplığı algoritmalarının kuralları ve terminolojisi açıklanmaktadır.

## <a name="remarks"></a>Açıklamalar

Algoritma şablonu işlevlerinin açıklamaları çeşitli toplu tümceler üzerinde çalışır:

- "A aralığındaki" ifadesi \[ , *b*) ile başlayan ancak *b* dahil değil, sıfır veya daha fazla ayrık değer dizisi  anlamına gelir. Bir Aralık, yalnızca *B* 'den ulaşılabiliyorsa geçerlidir *;* *bir* nesne *N* (*n* A) içinde bir nesne saklayabilir  =  , nesneyi sıfır veya daha fazla kez artırıp (+ +*n*), sınırlı sayıda artım (  *n*  ==  *B*) sonra nesne karşılaştırmasını eşittir.

- "A aralığındaki her *N* \[ , *B*)" ifadesi, *N* değerinin *a* ile başladığı ve *b* değerine eşit olana kadar sıfır veya daha fazla kez artırılan bir ifade anlamına gelir. *N*  ==  *B* , Aralık içinde değil.

- "A, b aralığındaki en düşük *n* değeri \[ , *b*" ifadesi *, x değeri* karşılanana kadar *x* koşulu, b aralığındaki her *N* için belirlenir \[ .  

- "A, b aralığındaki en yüksek *n* değeri \[ , *b*) *, x 'in*   \[ *a*, *b* aralığındaki her n için belirlendiği anlamına gelir. İşlevi, *X* koşulu her karşılandığında *N* bir kopyasını *K* içinde depolar. Böyle bir mağaza gerçekleşirse, *işlev,* K değeri olan *N*'Nin son değerini, *K* değeri ile değiştirir. Bununla birlikte çift yönlü veya rastgele erişim Yineleyici için, *N* 'nin aralıktaki en yüksek değerle başlaması ve *X* koşulu karşılanıncaya kadar aralığa göre azaltılabileceği anlamına da gelir.

- X ve Y *gibi ifadeler*  -  Rastgele erişimli  yineleyiciler  dışında yineleyiciler olabilir, matematik açısından tasarlanmıştır. İşlevin **-** Bu tür bir değeri belirlemesi gerekiyorsa işleç değerlendirmesi gerekmez. Aynı zamanda *x*  +  *n* ve *x* n gibi ifadeler için de geçerlidir  -  ; burada *N* bir tamsayı türüdür.

Birçok algoritma, bir sonuç sağlamak için gibi ikili bir karşılaştırma gerçekleştiren bir koşul kullanır `operator==` **`bool`** . Koşul işlevi `operator==` veya bunun herhangi bir değişikliği, işlenenlerinin birini değiştirmemelidir. **`bool`** Her değerlendirildiğinde aynı sonucu vermelidir ve iki işlenenin bir kopyası işlenenin yerini aldığında aynı sonucu vermelidir.

Çeşitli algoritmalar, bir dizideki öğe çiftlerine katı zayıf bir sıralama gerçekleştiren bir koşul kullanır. *Pred*(*X*, *Y*) koşulu için:

- Katı, *Pred*'nin (*x*, *x*) yanlış olduğu anlamına gelir.

- Zayıf,   \! *Pred*(*x*, *Y*)  && \! *Pred*(*y*, *x*) (*x*  ==  *Y* 'nin tanımlanması gerekmiyorsa), x ve y 'nin eşdeğer bir sıralama olduğu anlamına gelir.

- Sıralama, *Pred (**x*, *Y*)  && *Pred*(*y*, *z*) ile *Pred*(*x*, *z*) anlamına gelir.

Bu algoritmalardan bazıları örtük olarak *X* \< *Y*. Other predicates that typically satisfy the strict weak ordering requirement are *X* > *Y*, `less` (*x*, *y*) ve `greater` (*x*, *y*) koşulunu kullanır. Ancak, *X* \<= *Y* and *X* > =  *Y* gibi koşulların bu gereksinimi karşılamadığını unutmayın.

İlk olarak aralıktaki yineleyiciler tarafından belirlenen bir dizi öğe, \[   **<**  \[ 0, *son*  -  *ilk*) ve aralıktaki her bir N için (*n*,  *son*  -  *ilk*) koşul \! ( \* (*ilk* olarak)  +  < \* (*ilk*  +  *N*)) true ise işleçle sıralanan bir sıralamadır. (Öğelerin artan sırada sıralanacağını unutmayın.) Koşul işlevi `operator<` veya bunun herhangi bir değişikliği, işlenenlerinin birini değiştirmemelidir. **`bool`** Her değerlendirildiğinde aynı sonucu vermelidir ve iki işlenenin bir kopyası işlenenin yerini aldığında aynı sonucu vermelidir. Üstelik, karşılaştırıldığı işlenenler üzerinde katı bir zayıf sıralama getirmelidir.

Aralık içinde yineleyiciler tarafından belirlenen öğelerin bir dizisi \[ `First` , `Last` `operator<` 1. Aralık içindeki her *N* için, \[ *en son*  -  *ilk başta*) koşulun \! (ilk \*   <  \* (*ilk*  +  *n*)) doğru olması halinde sıralı bir yığın olur. (İlk öğe en genişdir.) İç yapısı başka bir şekilde yalnızca [make_heap](algorithm-functions.md#make_heap), [pop_heap](algorithm-functions.md#pop_heap)ve [Push_heap](algorithm-functions.md#push_heap)şablon işlevleri için de bilinir. Sıralı bir dizide, koşul işlevinde `operator<` veya herhangi bir değişiklik için, işlenenlerinin birini değiştirmemelidir ve karşılaştırıldığı işlenenler üzerinde katı bir zayıf sıralama getirmelidir. **`bool`** Her değerlendirildiğinde aynı sonucu vermelidir ve iki işlenenin bir kopyası işlenenin yerini aldığında aynı sonucu vermelidir.

C++ Standart Kitaplığı algoritmaları [\<algorithm>](algorithm.md) ve [\<numeric>](numeric.md) üst bilgi dosyalarında bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı başvurusu](cpp-standard-library-reference.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)
