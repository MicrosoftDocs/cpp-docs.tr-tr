---
title: Algoritmalar
ms.date: 10/18/2018
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
ms.openlocfilehash: d363dc3f06222121ac5efc79b30516ebd55ff539
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456492"
---
# <a name="algorithms"></a>Algoritmalar

Algoritmalar C++ standart kitaplığın temel bir parçasıdır. Algoritmalar, kapsayıcılarla, ancak yineleyiciler ile çalışmaz. Bu nedenle, tüm C++ standart kitaplık kapsayıcılarından biri olmadığı için aynı algoritma çok büyük bir şekilde kullanılabilir. Bu bölümde C++ standart kitaplık algoritmalarının kuralları ve terminolojisi açıklanmaktadır.

## <a name="remarks"></a>Açıklamalar

Algoritma şablonu işlevlerinin açıklamaları çeşitli toplu tümceler üzerinde çalışır:

- " \[ *A*aralığındaki" ifadesi, *b* *) ile başlayan* ancak *b*dahil değil, sıfır veya daha fazla ayrık değer dizisi anlamına gelir. Bir Aralık, yalnızca *b* 'den ulaşılabiliyorsa geçerlidir *;* bir nesne *N* (*n* = *A*) içinde *bir* nesne saklayabilir, nesneyi sıfır veya daha fazla kez artırın (+ +*N*) ve nesne karşılaştırması için *B* 'ye eşittir sınırlı sayıda artımdan (*N* == *B*) sonra.

- " *A*aralığındaki \[her *N* , *B*)" ifadesi, *N* değerinin *a* ile başladığı ve *b*değerine eşit olana kadar sıfır veya daha fazla kez artırılan bir ifade anlamına gelir. *N* == *B* , Aralık içinde değil.

- " *A*, b aralığındaki \[ \[en düşük *N* değeri, b *" ifadesi*, x işareti, *a*, *b*) koşul *X* karşılandı.

- " *A*, b aralığındaki \[en yüksek *n* değeri, *b*), x 'in *a*, *b*aralığındaki \[her *n* için *belirlendiği anlamına gelir* . İşlevi, *X* koşulu her karşılandığında *N* bir kopyasını *K* içinde depolar. Böyle bir mağaza gerçekleşirse, işlev, K değeri olan *N*'nin son değerini, *K*değeriile değiştirir. Bununla birlikte çift yönlü veya rastgele erişim Yineleyici için, *N* 'nin aralıktaki en yüksek değerle başlaması ve *X* koşulu karşılanıncaya kadar aralığa göre azaltılabileceği anlamına da gelir.

- X ve Y gibi ifadeler Rastgele erişimli yineleyiciler dışında yineleyiciler olabilir, matematik açısından tasarlanmıştır. -  İşlevin bu tür bir değeri belirlemesi gerekiyorsa **-** işleç değerlendirmesi gerekmez. Aynı zamanda *x* + *n* ve *x* - *n*gibi ifadeler için de geçerlidir; burada *N* bir tamsayı türüdür.

Birçok algoritma, ile `operator==`gibi ikili bir karşılaştırma gerçekleştiren bir koşulu **bool** sonucu verecek şekilde kullanır. Koşul işlevi `operator==`veya bunun herhangi bir değişikliği, işlenenlerinin birini değiştirmemelidir. Her değerlendirildiğinde aynı **bool** sonucunu vermelidir ve iki işlenenin bir kopyası işlenenin yerini aldığında aynı sonucu vermelidir.

Çeşitli algoritmalar, bir dizideki öğe çiftlerine katı zayıf bir sıralama gerçekleştiren bir koşul kullanır. *Pred*(*X*, *Y*) koşulu için:

- Katı, *Pred*'nin (*x*, *x*) yanlış olduğu anlamına gelir.

- Zayıf olduğunda, \! *Pred*(*x*, *y*) & \!& *Pred*(*y*, *x*) (*x* == *Y* değilse) için eşit bir *sıralama olduğu anlamına* gelir. tanımlanması gerekir).

- Sıralama, Pred (*x*, *Y*) & & *Pred*(*y*, *z*) ile *Pred*(*x*, *z*) anlamına gelir.

Bu algoritmalardan bazıları örtük olarak *X* \< *Y*koşulunu kullanır. Genellikle katı zayıf sıralama gereksinimini karşılayan diğer koşullar *X* > *Y* `less`, (*x*, *y*) `greater`ve (*x*, *y*). Ancak, *x* \< yve >= x*y* gibi koşulların bu gereksinimi karşılamadığını unutmayın. = 

\[ *İlk* -  \[ başta Aralık içinde yineleyiciler tarafından belirlenen bir dizi öğe, 0, son ilk, 0. aralıktaki her N için **<** ) ve aralıktaki her bir *e* (*N*, *son* - *ilk* \!) koşul (\*(*ilk* + *olarak) <* \*(İlk + *N*)) true. (Öğelerin artan sırada sıralanacağını unutmayın.) Koşul işlevi `operator<`veya bunun herhangi bir değişikliği, işlenenlerinin birini değiştirmemelidir. Her değerlendirildiğinde aynı **bool** sonucunu vermelidir ve iki işlenenin bir kopyası işlenenin yerini aldığında aynı sonucu vermelidir. Üstelik, karşılaştırıldığı işlenenler üzerinde katı bir zayıf sıralama getirmelidir.

Aralık \[ -  \[içinde yineleyiciler tarafından belirlenen bir dizi öğe,, 1 Aralık içinde her N için, son önce `First` `Last` `operator<` koşul \!(\*_ilk_ *(ilk*N))doğru. < \* +  (İlk öğe en genişdir.) İç yapısı, diğer koşullarda yalnızca [make_heap](../standard-library/algorithm-functions.md#make_heap), [pop_heap](../standard-library/algorithm-functions.md#pop_heap)ve [Push_heap](../standard-library/algorithm-functions.md#push_heap)şablon işlevleri için de bilinir. Sıralı bir dizide, koşul işlevinde `operator<`veya herhangi bir değişiklik için, işlenenlerinin birini değiştirmemelidir ve karşılaştırıldığı işlenenler üzerinde katı bir zayıf sıralama getirmelidir. Her değerlendirildiğinde aynı **bool** sonucunu vermelidir ve iki işlenenin bir kopyası işlenenin yerini aldığında aynı sonucu vermelidir.

C++ Standart kitaplık algoritmaları [ \<algoritma >](../standard-library/algorithm.md) ve [ \<sayısal >](../standard-library/numeric.md) üst bilgi dosyalarında bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[C++Standart kitaplık başvurusu](../standard-library/cpp-standard-library-reference.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
