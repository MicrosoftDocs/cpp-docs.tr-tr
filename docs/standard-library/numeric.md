---
title: '&lt;Sayısal&gt;'
ms.date: 11/04/2016
f1_keywords:
- <numeric>
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
ms.openlocfilehash: ce195742605c3dd2e127c84ac2f4e1e696c75bd0
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246690"
---
# <a name="ltnumericgt"></a>&lt;Sayısal&gt;

Sayısal işlemeler için algoritmalar gerçekleştiren kapsayıcı şablon işlevini tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<sayısal >

**Namespace:** std

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı algoritmalara sayısal algoritmalarının benzer [ \<algoritma >](algorithm.md)ve çeşitli veri yapıları üzerinde çalışabilir. Bu standart kitaplığı kapsayıcı sınıflarını içerir — örneğin, [vektör](../standard-library/vector-class.md) ve [listesi](../standard-library/list-class.md)ve program tarafından tanımlı veri yapılarını ve dizi belirli algoritma gereksinimlerini karşılayan bir öğe. Algoritmalar dolaylı olarak yineleyiciler üzerinden bir kapsayıcının öğelerine erişerek ve geçiş yaparak bu genellik düzeyine erişir. Algoritmalar genellikle kendi başlangıç veya bitiş konumları tarafından belirtilen yineleyici aralıklarını işler. Aralıklardaki tüm işaretçilerin tekrar başvurulabilir olması ve her aralığın dizisinde olması gerekliliği bakımından, başvurulan aralıkların geçerli olması gerekir; son konum da artış yoluyla birinciden erişilebilir olmalıdır.

Algoritmalar işlemleri ve her birinin C++ Standart Kitaplığı kapsayıcıları üye işlevleri tarafından desteklenir ve aynı anda farklı kapsayıcı nesne türlerine ile etkileşimi etkinleştirmek eylemleri genişletir.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[accumulate](../standard-library/numeric-functions.md#accumulate)|Art arda gelen kısmi toplamları ya da toplama işlemi yerine belirtilmiş bir ikili işlem kullanılarak elde edilen art arda gelen kısmi sonuçların sonucunu hesaplayarak belirtilen aralıktaki tüm öğelerin, bazı başlangıç değerleri de dahil olmak üzere, toplamını hesaplar.|
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|
|[exclusive_scan](../standard-library/numeric-functions.md#exclusive_scan)||
|[gcd](../standard-library/numeric-functions.md#gcd)||
|[inclusive_scan](../standard-library/numeric-functions.md#inclusive_scan)||
|[inner_product](../standard-library/numeric-functions.md#inner_product)|İki aralığın öğe düzeyinde çarpımının toplamını hesaplar ve bunu belirtilen başlangıç değerine ekler veya ürün işlemlerinin başka bir belirtilen ikili işlem tarafından değiştirildiği toplamın ve ürün işlemlerinin genelleştirilmiş bir sonucunu hesaplar.|
|[iota](../standard-library/numeric-functions.md#iota)|İlk öğe ile başlayan ve değeri art arda gelen artışlarla dolduran bir başlangıç değeri depolar (`value++`) aralığındaki öğelerin her `[first, last)`.|
|[lcm](../standard-library/numeric-functions.md#lcm)||
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|Bir öğeyi kullanarak ilk öğedeki bir giriş aralığında hesaplar *miyim*öğedeki ve her bir toplamın sonucunu depolar *miyim*öğedeki bir hedef aralığına veya genelleştirilmiş bir sonucunu hesaplar. Belirtilen ikili işlemde yordamı toplama işleminin başka bir yere değiştirilir.|
|[azaltın](../standard-library/numeric-functions.md#reduce)||
|[transform_exclusive_scan](../standard-library/numeric-functions.md#transform_exclusive_scan)||
|[transform_inclusive_scan](../standard-library/numeric-functions.md#transform_inclusive_scan)||
|[transform_reduce](../standard-library/numeric-functions.md#transform_reduce)||

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
