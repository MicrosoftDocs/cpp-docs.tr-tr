---
title: Algoritmalar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bc9d57f93b5d3ee537330ab16c2c9a02b6beead
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="algorithms"></a>Algoritmalar
Algoritmalar, C++ Standart Kitaplığı, temel bir parçasıdır. Algoritmalar kapsayıcıları kendilerini ile ancak bunun yerine yineleyiciler çalışmaz. Bu nedenle, aynı algoritmayı çoğu değilse tarafından tüm C++ Standart Kitaplığı kapsayıcıları kullanılabilir. Bu bölüm, C++ Standart Kitaplığı algoritmalarının terminoloji ve kuralları açıklar.  
  
## <a name="remarks"></a>Açıklamalar  
 Algoritma şablon işlevleri açıklamalarını birkaç kestirme tümcecikleri birkaçını:  
  
-   Tümcecik "aralığında [*A*, *B*)" ile başlayan sıfır veya daha fazla ayrık değerler dizisi anlamına gelir *A* kadar ancak dahil değil *B*. Bir aralığı geçerli yalnızca *B* gelen erişilebildiğinden *A;* depolayabileceğiniz *A* nesnedeki *N* (*N*  =  *A*), sıfır veya daha fazla kez nesne Artır (++*N*), ve eşit Karşılaştır nesnesi *B* artışlarla sınırlı sayıda sonra (N B==*).*  
  
-   Tümcecik "her *N* aralığında [*A*, *B*)" anlamına *N* değerle başlayan *A* ve değerine eşit kadar sıfır veya daha fazla kez artar *B*. Durum *N* == *B* aralığında değil.  
  
-   Tümcecik "en düşük değerini *N* aralığında [*A*, *B*) gibi *X*" koşul anlamına *X*her biri için belirlenen *N* aralığında [*A*, *B*) koşul kadar *X* karşılanır.  
  
-   Tümcecik "en yüksek değeri *N* aralığında [*A*, *B*) gibi *X* anlamına *X* olduğu her biri için belirlenen *N* aralığında [*A*, *B*). İşlev depolar `K` bir kopyasını *N* koşul her zaman *X* karşılanır. Bu tür bir depolama meydana gelirse, işlevi son değerini değiştirir *N*, hangi eşittir *B*, değeriyle `K`. Çift yönlü veya rasgele erişim Yineleyici, ancak bu, anlamına da gelebilir *N* aralığındaki en yüksek değer ile başlar ve aralığında kadar koşul düşülür *X* karşılanır.  
  
-   İfadeler gibi *X* - *Y*, burada *X* ve *Y* tasarlanmıştır, rastgele erişim yineleyiciler dışında yineleyiciler olabilir Matematik anlamda. İşlev işleci değerlendirmek değil **-**  varsa bu tür bir değer belirlemelisiniz. Aynı ayrıca ifadeler için doğru olduğu gibi *X* + *N* ve *X* - *N*, burada *N*  bir tamsayı türüdür.  
  
 Çeşitli algoritmalar olun ile gibi ikili karşılaştırma gerçekleştiren bir koşul kullanımı `operator==`, elde etmek üzere bir `bool` sonucu. Koşul işlevi `operator==`, ya da ona ait tüm değiştirme gerekir değiştirmemesi işlenenleri birini. Aynı verim gerekir `bool` kabul edilir ve her iki işlenen bir kopyasını işleneni yerine, aynı sonucu verecek gerekir her zaman sonucu.  
  
 Çeşitli algoritmalar olun, bir katı zayıf bir sırasından öğelerinin çiftleri sıralama zorunlu tuttukları gerekir bir koşulun kullanın. Koşul için `pr`(*X*, *Y*):  
  
-   Strict anlamına `pr`(*X*, *X*) yanlış.  
  
-   Zayıf anlamına *X* ve *Y* eşdeğer bir sıralama konusuysa!`pr` (*X*, *Y*) & &!`pr` (*Y*, *X*) (*X* == *Y* tanımlanması gerekmez).  
  
-   Sıralama anlamına `pr`(*X*, *Y*) & & `pr`(*Y*, Z) gelir `pr`(*X*, Z).  
  
 Bu algoritmalar bazıları örtük olarak koşulu kullanmak *X* \< *Y*. Genellikle gereksinim sıralama katı zayıf karşılamak diğer koşulları olan *X* > *Y*, **daha az**(*X*,  *Y*), ve `greater`(*X*, *Y*). Unutmayın, ancak bu doğrulamaları gibi *X* \< =  *Y* ve *X* >= *Y* uygun olmadığı Bu gereksinim.  
  
 Yineleyiciler aralığında belirlenen öğeleri dizisi [`First`, `Last`) operatörü tarafından sıralanan sırası **<**  her IF *N* aralığında [0, `Last`  -  `First`) ve her *M* aralığında (N `Last`  -  `First`) koşulu! () \*(`First` + *M*) < \*(*ilk* + *N*)) geçerlidir. (Öğeleri artan düzende sıralanır unutmayın.) Koşul işlevi **işleci <**, ya da ona ait tüm değiştirme gerekir değiştirmemesi işlenenleri birini. Aynı verim gerekir `bool` kabul edilir ve her iki işlenen bir kopyasını işleneni yerine, aynı sonucu verecek gerekir her zaman sonucu. Ayrıca, katı bir zayıf onu karşılaştırır işlenen üzerinde sıralama koymak gerekir.  
  
 Yineleyiciler aralığında belirlenen öğeleri dizisi [`First`, `Last`) yığın göre sıralanmış **işleci <** her IF *N* aralığında [1, `Last`  -  `First`) koşulu! (\*`First` < \*(`First` + *N*)) geçerlidir. (İlk öğesi, en büyük olur.) İç yapısını Aksi halde yalnızca şablon işlevleri bilinen [make_heap](../standard-library/algorithm-functions.md#make_heap), [pop_heap](../standard-library/algorithm-functions.md#pop_heap), ve [push_heap](../standard-library/algorithm-functions.md#push_heap). Sıralı, koşul işlevinin olduğu gibi **işleci <**, veya ona ait tüm değiştirme gerekir değiştirmemesi işlenenleri birini ve katı bir zayıf onu karşılaştırır işlenen üzerinde sıralama koymak gerekir. Aynı verim gerekir `bool` kabul edilir ve her iki işlenen bir kopyasını işleneni yerine, aynı sonucu verecek gerekir her zaman sonucu.  
  
 C++ Standart Kitaplığı algoritmaları bulunan [ \<algoritması >](../standard-library/algorithm.md) ve [ \<sayısal >](../standard-library/numeric.md) üstbilgi dosyaları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

