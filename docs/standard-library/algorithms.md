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
ms.openlocfilehash: a0a1165d731e44568d530e3ed919d73e2a3e8e5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648038"
---
# <a name="algorithms"></a>Algoritmalar

Algoritmalar, C++ Standart Kitaplığı, temel bir parçasıdır. Algoritmalar, kendilerini kapsayıcılar ile ancak yineleyiciler yerine ile çalışmaz. Bu nedenle, aynı algoritmayı en değilse tarafından tüm C++ Standart Kitaplığı kapsayıcıları kullanılabilir. Bu bölüm, C++ Standart Kitaplığı algoritmaları terminoloji ve kuralları açıklar.

## <a name="remarks"></a>Açıklamalar

Algoritma şablon işlevleri açıklamalarını birkaç toplu ifadeleri kullanın:

- İfade "aralığında \[ *A*, *B*)" ile başlayan sıfır veya daha fazla ayrık değerler dizisi anlamına gelir *bir* kadar ancak dahil değil *B* . Geçerli bir aralık olduğundan yalnızca *B* Sunucusu'ndan olan *A;* depolayabilir miyim *bir* nesnedeki *N* (*N*  =  *A*), nesne sıfır veya daha fazla kez Artır (++*N*), ve eşit Karşılaştır nesnesinin *B* sınırlı bir artış sayısını sonra (*N*   ==  *B*).

- İfade "her *N* aralığında \[ *A*, *B*)" anlamına gelir *N* değer ile başlayan *bir*ve değeri eşittir kadar sıfır veya daha fazla kez artırılır *B*. Durum *N* == *B* aralığında değil.

- İfade "en düşük değerini *N* aralığında \[ *A*, *B*) gibi *X*" koşul anlamına*X* her biri için belirlenen *N* aralığında \[ *A*, *B*) koşul kadar *X*karşılanır.

- İfade "en yüksek değeri *N* aralığında \[ *A*, *B*) gibi *X* anlamına *X* her biri için belirlenen *N* aralığında \[ *A*, *B*). İşlev depolar *K* bir kopyasını *N* koşul her zaman *X* karşılanır. Bu tür bir depolama ortaya çıkarsa, işlev son değerini değiştirir *N*, hangi eşittir *B*, değeriyle *K*. Çift yönlü veya rastgele erişim yineleyicisini, ancak bu, anlamına da gelebilir *N* aralıktaki en yüksek değeri ile başlayan ve koşul kadar aralığında azaltılır *X* karşılanır.

- İfadeler gibi *X* - *Y*burada *X* ve *Y* yöneliktir, rasgele erişim yineleyicileri dışında yineleyiciler olabilir matematiksel anlamda. İşlev işleci değerlendirmek değil **-** varsa, bu tür bir değer belirlemelisiniz. Aynı de gibi ifadeler için geçerlidir *X* + *N* ve *X* - *N*burada *N*  bir tamsayı türüdür.

Birçok algoritma olun ile olduğu gibi bir ikili karşılaştırma gerçekleştiren bir koşul kullanmak `operator==`, elde etmek üzere bir **bool** sonucu. Koşul işlevi `operator==`, ya da herhangi bir ardılı gerekir değiştirmemesi işlenenleri biri. Aynı yield gerekir **bool** her zaman değerlendirilir ve iki işlenenden kopyası için işlenen konur, aynı sonucu verecek gerekir neden.

Birçok algoritma olun katı bir zayıf çiftlerini dizisinin öğelerinin sıralama dayatır bir koşul kullanın. Koşul için *pred*(*X*, *Y*):

- Katı anlamına *pred*(*X*, *X*) yanlış.

- Zayıf anlamına *X* ve *Y* eşdeğer bir sıralama söz konusuysa \! *pred*(*X*, *Y*) & & \! *pred*(*Y*, *X*) (*X* == *Y*tanımlanması gerekmez).

- Sıralama anlamına *pred*(*X*, *Y*) & & *pred*(*Y*, *Z*) gelir *pred*(*X*, *Z*).

Bu algoritmalar bazıları örtük olarak koşul kullanmak *X* \< *Y*. Gereksinim sıralama katı zayıf genellikle karşılayan diğer koşullar olan *X* > *Y*, `less`(*X*, *Y*), ve `greater`(*X*, *Y*). Unutmayın, Bununla birlikte, doğrulamaları gibi *X* \< =  *Y* ve *X* >= *Y* karşılamaz Bu gereksinim.

Bir dizi öğe aralığındaki yineleyiciler tarafından belirlenen \[ *ilk*, *son*) işleciyle sıralı bir dizisi olduğundan **<** örneğin her  *N* aralığında \[0 *son* - *ilk*) ve her *M* aralığındaki (*N*, *Son* - *ilk*) koşul \!(\*(*ilk*  +  *M*) < \*(*ilk* + *N*)) geçerlidir. (Öğeleri artan düzende sıralanır unutmayın.) Koşul işlevi `operator<`, ya da herhangi bir ardılı gerekir değiştirmemesi işlenenleri biri. Aynı yield gerekir **bool** her zaman değerlendirilir ve iki işlenenden kopyası için işlenen konur, aynı sonucu verecek gerekir neden. Ayrıca, katı bir zayıf karşılaştırır, işlenenler üzerinde sıralama dayatır gerekir.

Bir dizi öğe aralığındaki yineleyiciler tarafından belirlenen \[ `First`, `Last`) bir yığın tarafından bulunduğundan `operator<` her ise *N* aralığında \[1, *enson*  -  *İlk*) koşul \!(\*_ilk_ < \*(*ilk*  +  *N*)) geçerlidir. (İlk öğenin en büyük içindir.) İç yapısını Aksi durumda yalnızca şablon işlevlerine bilinen [make_heap](../standard-library/algorithm-functions.md#make_heap), [pop_heap](../standard-library/algorithm-functions.md#pop_heap), ve [push_heap](../standard-library/algorithm-functions.md#push_heap). Bir sıralı koşul işlevi olduğu gibi `operator<`, herhangi bir ardılı gerekir değiştirmemesi işlenenleri birini veya katı bir zayıf karşılaştırır, işlenenler üzerinde sıralama dayatır gerekir. Aynı yield gerekir **bool** her zaman değerlendirilir ve iki işlenenden kopyası için işlenen konur, aynı sonucu verecek gerekir neden.

C++ Standart Kitaplığı algoritmaları bulunan [ \<algoritma >](../standard-library/algorithm.md) ve [ \<sayısal >](../standard-library/numeric.md) üst bilgi dosyaları.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
