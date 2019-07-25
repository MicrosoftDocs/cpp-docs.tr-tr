---
title: '&lt;rakamlardan&gt;'
ms.date: 11/04/2016
f1_keywords:
- <numeric>
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
ms.openlocfilehash: 5862ddd812308c7bf81a5029249caf7e9b4a1168
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453549"
---
# <a name="ltnumericgt"></a>&lt;rakamlardan&gt;

Sayısal işlemeler için algoritmalar gerçekleştiren kapsayıcı şablon işlevini tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<sayısal >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Sayısal algoritmalar, C++ [ \<algoritma >](algorithm.md)standart kitaplık algoritmalarına benzer ve çeşitli veri yapıları üzerinde çalışabilir. Bunlar arasında standart kitaplık kapsayıcı sınıfları vardır — örneğin, [vektör](../standard-library/vector-class.md) ve [liste](../standard-library/list-class.md), program tanımlı veri yapıları ve belirli bir algoritmanın gereksinimlerini karşılayan öğelerin dizileri. Algoritmalar dolaylı olarak yineleyiciler üzerinden bir kapsayıcının öğelerine erişerek ve geçiş yaparak bu genellik düzeyine erişir. Algoritmalar genellikle kendi başlangıç veya bitiş konumları tarafından belirtilen yineleyici aralıklarını işler. Aralıklardaki tüm işaretçilerin tekrar başvurulabilir olması ve her aralığın dizisinde olması gerekliliği bakımından, başvurulan aralıkların geçerli olması gerekir; son konum da artış yoluyla birinciden erişilebilir olmalıdır.

Algoritmalar, her bir C++ standart kitaplık kapsayıcısının işlemler ve üye işlevleri tarafından desteklenen eylemleri genişletir ve aynı anda farklı kapsayıcı nesne türleriyle etkileşimi etkinleştirir.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[accumulate](../standard-library/numeric-functions.md#accumulate)|Art arda gelen kısmi toplamları ya da toplama işlemi yerine belirtilmiş bir ikili işlem kullanılarak elde edilen art arda gelen kısmi sonuçların sonucunu hesaplayarak belirtilen aralıktaki tüm öğelerin, bazı başlangıç değerleri de dahil olmak üzere, toplamını hesaplar.|
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|Her bir öğe arasındaki art arda gelen farkları ve bir giriş aralığındaki kendi öncellerini hesaplar ve bir hedef aralığında sonuçların çıktısını alır veya fark işleminin başka bir belirtilen bir ikili işlem tarafından değiştirildiği genelleştirilmiş bir yordamın sonucunu hesaplar.|
|[exclusive_scan](../standard-library/numeric-functions.md#exclusive_scan)||
|[GCD](../standard-library/numeric-functions.md#gcd)||
|[inclusive_scan](../standard-library/numeric-functions.md#inclusive_scan)||
|[inner_product](../standard-library/numeric-functions.md#inner_product)|İki aralığın öğe düzeyinde çarpımının toplamını hesaplar ve bunu belirtilen başlangıç değerine ekler veya ürün işlemlerinin başka bir belirtilen ikili işlem tarafından değiştirildiği toplamın ve ürün işlemlerinin genelleştirilmiş bir sonucunu hesaplar.|
|[harfi](../standard-library/numeric-functions.md#iota)|İlk öğeden başlayarak ve aralıktaki`value++` `[first, last)`öğelerin her birinde () değerin birbirini izleyen artışlarıyla doldurarak başlangıç değerini depolar.|
|[LCM](../standard-library/numeric-functions.md#lcm)||
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|İlk öğeden *i*. öğe aracılığıyla bir giriş aralığındaki bir dizi toplamı hesaplar ve her toplamın sonucunu bir hedef aralığın *i*. öğesinde depolar ya da toplam işlemin sonucu olan genelleştirilmiş bir yordamın sonucunu hesaplar belirtilen başka bir ikili işlem tarafından değiştirilmiş.|
|[azal](../standard-library/numeric-functions.md#reduce)||
|[transform_exclusive_scan](../standard-library/numeric-functions.md#transform_exclusive_scan)||
|[transform_inclusive_scan](../standard-library/numeric-functions.md#transform_inclusive_scan)||
|[transform_reduce](../standard-library/numeric-functions.md#transform_reduce)||

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
