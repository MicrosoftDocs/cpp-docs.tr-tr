---
title: '&lt;valarray&gt;'
ms.date: 11/04/2016
f1_keywords:
- <valarray>
helpviewer_keywords:
- valarray header
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
ms.openlocfilehash: 9154f15500863d815f56438090662416b9b6fe7f
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246652"
---
# <a name="ltvalarraygt"></a>&lt;valarray&gt;

Şablon sınıfı valarray ve çok sayıda destekleyici şablon sınıfları ve işlevleri tanımlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

> [!NOTE]
> \<Valarray > kitaplığını kullanan ' # < initializer_list > include' deyimi.

## <a name="remarks"></a>Açıklamalar

Bu şablonu sınıfları ve işlevleri, Gelişmiş performans açısından olağan dışı enlem izin verilir. Özellikle türü döndüren bir işlev `valarray<T1>` türünde bir nesne bazı diğer T2 döndürebilir. Bu durumda, herhangi bir veya daha fazla bağımsız değişken türü kabul eden işlev `valarray<T2>` rasgele bağımsız değişkenleri, bağımsız değişken T2 türü ile her değiştirilen birleşimlerini kabul eden aşırı yüklemeler olması gerekir.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Abs](../standard-library/valarray-functions.md#abs)|Öğeleri girdi valarray öğelerini mutlak değerini eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[acos](../standard-library/valarray-functions.md#acos)|Öğeleri girdi valarray öğelerini arkkosinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[asin](../standard-library/valarray-functions.md#asin)|Öğeleri girdi valarray öğelerini sinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[atan](../standard-library/valarray-functions.md#atan)|Öğeleri girdi valarray öğelerini arktanjantını asıl değerine eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[atan2](../standard-library/valarray-functions.md#atan2)|Öğeleri arktanjantını Kartezyen için eşit olan bir valarray sabitler birleşimi ve valarrays öğeleri tarafından belirtilen bileşenlerini döndürür.|
|[başlayın](../standard-library/valarray-functions.md#begin)||
|[cos](../standard-library/valarray-functions.md#cos)|Öğeleri girdi valarray öğelerini kosinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[COSH](../standard-library/valarray-functions.md#cosh)|Öğeleri girdi valarray öğelerini hiperbolik kosinüsünü için eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[Son](../standard-library/valarray-functions.md#end)||
|[exp](../standard-library/valarray-functions.md#exp)|Öğeleri girdi valarray öğelerinin üstel doğal eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[log](../standard-library/valarray-functions.md#log)|Öğeleri için doğal logaritmasını giriş valarray öğelerinin eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[log10](../standard-library/valarray-functions.md#log10)|Öğeleri taban 10 ya da ortak logaritmasını giriş valarray öğelerinin eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[POW](../standard-library/valarray-functions.md#pow)|Giriş valarrays ve öğeleri bir tabana eşit olan bir valarray ya da bir giriş valarray öğelerini belirtilen ya da bir üssü bir sabit ya da bir giriş valarray öğelerini belirtilen döndüren sabitleri, öğeler üzerinde çalışır veya sabit değer.|
|[sin](../standard-library/valarray-functions.md#sin)|Öğeleri girdi valarray öğelerini sinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[SİNH](../standard-library/valarray-functions.md#sinh)|Öğeleri girdi valarray öğelerini hiperbolik sinüsünü için eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[sqrt](../standard-library/valarray-functions.md#sqrt)|Öğeleri girdi valarray öğelerini kare kökünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[değiştirme](../standard-library/valarray-functions.md#swap)||
|[tan](../standard-library/valarray-functions.md#tan)|Öğeleri girdi valarray öğelerini tanjantını eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[TANH](../standard-library/valarray-functions.md#tanh)|Öğeleri girdi valarray öğelerini hiperbolik tanjantını için eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/valarray-operators.md#op_neq)|Eşit değil veya bir valarray tüm öğelerini eşit olup iki eşit boyutlu valarrays karşılık gelen öğeleri olup olmadığını test eder valarray'nın öğe türünün belirtilen bir değer.|
|[operator%](../standard-library/valarray-operators.md#op_mod)|Valarray'nın öğe türünün veya bir valarray tarafından belirtilen değere bölerek belirtilen değerle bir valarray ayırma iki eşit boyutlu valarrays ve karşılık gelen öğelerle bölme kalanı alır.|
|[işleç &](../standard-library/valarray-operators.md#op_amp)|Bit düzeyinde alır `AND` bir valarray ve öğe türü belirtilen değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.|
|[operator & &](../standard-library/valarray-operators.md#op_amp_amp)|Mantıksal alır `AND` bir valarray ve valarray'nın öğe türünün belirtilen bir değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.|
|[operator >](../standard-library/valarray-operators.md#op_gt)|Bir valarray öğelerini öğelerini eşit boyutlu bir valarray veya bir valarray tüm öğelerini büyük veya valarray'nın öğe türünün belirtilen değerden daha az olup büyük olup olmadığını test eder.|
|[operator>=](../standard-library/valarray-operators.md#op_gt_eq)|Bir valarray öğelerini değerinden büyük veya eşit boyutlu bir valarray veya bir valarray tüm öğelerini büyük veya eşit veya daha az olup belirtilen bir değere eşit öğelerinin eşit olup olmadığını test eder.|
|[İşleç >>](../standard-library/valarray-operators.md#op_gt_gt)|Sağa kaydırmalar her öğeyi belirtilen sayıda konumları veya ikinci bir valarray tarafından belirtilen aralığın öğe düzeyinde çarpımının bir miktara göre bir valarray parçaları.|
|[işleç <](../standard-library/valarray-operators.md#op_lt)|Bir valarray öğelerinin eşit boyutlu bir valarray veya bir valarray tüm öğelerini büyük ya da belirtilen değerden daha az olup öğelerini küçük olup olmadığını test eder.|
|[operator < =](../standard-library/valarray-operators.md#op_lt_eq)|Bir valarray öğelerini ya da eşit boyutlu bir valarray öğelerinin eşit olup olmadığını veya bir valarray tüm öğelerini büyük veya eşit veya daha az veya belirtilen değere eşit olup olmadığını test eder.|
|[işleç <<](../standard-library/valarray-operators.md#op_lt_lt)|Sola bir valarray belirtilen sayıda konumları veya ikinci bir valarray tarafından belirtilen aralığın öğe düzeyinde çarpımının bir miktar, her öğe için bit kaydırır.|
|[operator *](../standard-library/valarray-operators.md#op_star)|Aralığın öğe düzeyinde çarpımının ürün arasındaki, iki eşit boyutlu valarrays ve karşılık gelen öğeleri alır bir valarray valarray'nın öğe türünün belirtilen bir değer arasında.|
|[operator +](../standard-library/valarray-operators.md#op_add)|İki eşit boyutlu valarrays veya, ilgili öğeler arasındaki aralığın öğe düzeyinde çarpımının toplamını alır bir valarray valarray'nın öğe türünün belirtilen bir değer arasında.|
|[operator-](../standard-library/valarray-operators.md#operator-)|İki eşit boyutlu valarrays veya, karşılık gelen öğeleri arasındaki aralığın öğe düzeyinde çarpımının fark alır bir valarray valarray'nın öğe türünün belirtilen bir değer arasında.|
|[operator /](../standard-library/valarray-operators.md#op_div)|Aralığın öğe düzeyinde çarpımının bölümü arasındaki, iki eşit boyutlu valarrays ve karşılık gelen öğeleri alır bir valarray valarray'nın öğe türünün belirtilen bir değer arasında.|
|[operator==](../standard-library/valarray-operators.md#op_eq_eq)|İki eşit boyutlu valarrays karşılık gelen öğeleri eşit veya bir valarray tüm öğelerini olup olup olmadığını test valarray'nın öğe türünün belirtilen değere eşit.|
|[operator ^](../standard-library/valarray-operators.md#op_xor)|Bit düzeyinde özel alır `OR` bir valarray ve öğe türü belirtilen değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.|
|[operator&#124;](../standard-library/valarray-operators.md#op_or)|Bit düzeyinde alır `OR` bir valarray ve öğe türü belirtilen değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.|
|[operator&#124;&#124;](../standard-library/valarray-operators.md#op_lor)|Mantıksal alır `OR` bir valarray ve valarray'nın öğe türünün belirtilen bir değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[gslice Sınıfı](../standard-library/gslice-class.md)|Çok boyutlu bir valarray Kesitler tanımlamak için kullanılan valarray için yardımcı program sınıfı.|
|[gslice_array Sınıfı](../standard-library/gslice-array-class.md)|Genel bir valarray dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak genel dilimi nesneleri destekleyen bir iç, yardımcı Şablon sınıfı.|
|[indirect_array Sınıfı](../standard-library/indirect-array-class.md)|Bir alt dizin üst valarray birini belirterek valarrays alt diziler arasındaki işlemleri sağlayarak kümeleridir destekler nesneleri tanımlanmış bir yardımcı, iç Şablon sınıfı.|
|[mask_array Sınıfı](../standard-library/mask-array-class.md)|Üst valarrays kümeleridir destekler nesnelerin alt diziler arasındaki işlemleri sağlayarak bir Boole ifadesi ile belirtilen bir iç, ikincil bir şablon sınıfı.|
|[slice Sınıfı](../standard-library/slice-class.md)|Valarray bir tek boyutlu, vektör benzeri alt kümelerini tanımlamak için kullanılan valarray için yardımcı program sınıfı.|
|[slice_array Sınıfı](../standard-library/slice-array-class.md)|Dilim nesneleri bir valarray dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak destekleyen bir iç, yardımcı Şablon sınıfı.|
|[valarray Sınıfı](../standard-library/valarray-class.md)|Şablon sınıfı bir dizi öğe türü denetleyen bir nesneyi tanımlayan `Type` , bir dizi olarak depolanır ve bu işlem performansına yönelik en iyi duruma getirilmiş hızlı matematik işlemlerini gerçekleştirmek için tasarlanmıştır.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[valarray\<bool > sınıfı](../standard-library/valarray-bool-class.md)|Özel bir şablon sınıfı valarray sürümü\<**türü**> türü öğeler için **bool**.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
