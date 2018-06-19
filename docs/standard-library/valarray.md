---
title: '&lt;valarray&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <valarray>
dev_langs:
- C++
helpviewer_keywords:
- valarray header
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 578dd43f747eddbf37f76c41a2fa35df8edca658
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862163"
---
# <a name="ltvalarraygt"></a>&lt;valarray&gt;

Şablon sınıfı valarray ve çok sayıda destekleyici şablon sınıfları ve işlevleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <valarray>

```

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfları ve işlevleri performansı gerçekleştirebiliriz olağan dışı enlem izin verilir. Özellikle, türü döndüren işlev **valarray\<** T1**>** türünde bir nesnenin bazı diğer T2 döndürebilir. Bu durumda, herhangi bir veya daha fazla bağımsız değişken türü kabul eden bir işlev **valarray\<** T2**>** bu bağımsız değişkenlerden rasgele birleşimlerini kabul aşırı olmalıdır her T2 türünde bir bağımsız değişken ile değiştirilir.

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[Abs](../standard-library/valarray-functions.md#abs)|Öğeleri girdi valarray öğelerini mutlak değerine eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[acos](../standard-library/valarray-functions.md#acos)|Öğeleri girdi valarray öğelerini arkkosinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[asin](../standard-library/valarray-functions.md#asin)|Öğeleri girdi valarray öğelerini sinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[atan](../standard-library/valarray-functions.md#atan)|Öğeleri girdi valarray öğelerini arktanjantını asıl değerine eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[atan2](../standard-library/valarray-functions.md#atan2)|Öğeleri arktanjantını Kartezyen için eşit olan bir valarray sabitler birleşimi ve valarrays öğeleri tarafından belirtilen bileşenleri döndürür.|
|[cos](../standard-library/valarray-functions.md#cos)|Öğeleri girdi valarray öğelerini kosinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[COSH](../standard-library/valarray-functions.md#cosh)|Öğeleri girdi valarray öğelerini hiperbolik kosinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[exp](../standard-library/valarray-functions.md#exp)|Öğeleri girdi valarray öğelerinin üstel doğal eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[log](../standard-library/valarray-functions.md#log)|Öğeleri için doğal logaritmasını giriş valarray öğelerinin eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[log10](../standard-library/valarray-functions.md#log10)|Öğeleri temel 10 veya ortak logaritmasını giriş valarray öğelerinin eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[POW](../standard-library/valarray-functions.md#pow)|Giriş valarrays ve öğeleri bir temel eşit olan bir valarray herhangi bir giriş valarray öğeler tarafından belirtilen veya bir üssü bir sabit ya da bir giriş valarray öğeler tarafından belirtilen döndürme sabitleri öğelerde çalışır veya sabiti.|
|[sin](../standard-library/valarray-functions.md#sin)|Öğeleri girdi valarray öğelerini sinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[SİNH](../standard-library/valarray-functions.md#sinh)|Öğeleri girdi valarray öğelerini hiperbolik sinüsünü eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[sqrt](../standard-library/valarray-functions.md#sqrt)|Öğeleri karekökünü giriş valarray öğelerinin eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[Değiştirme](../standard-library/valarray-functions.md#swap)||
|[tan](../standard-library/valarray-functions.md#tan)|Öğeleri girdi valarray öğelerini tanjantını eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|
|[TANH](../standard-library/valarray-functions.md#tanh)|Öğeleri girdi valarray öğelerini hiperbolik tanjantını eşit olan bir valarray döndüren bir giriş valarray öğeler üzerinde çalışır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/valarray-operators.md#op_neq)|İki eşit boyutta valarrays karşılık gelen öğelerini eşit olmayan veya olup olmadığını bir valarray tüm öğeleri eşit olup olmadığını sınar valarray's öğe türü belirtilen değeri.|
|[operator%](../standard-library/valarray-operators.md#op_mod)|Karşılık gelen öğeleri iki eşit boyutta valarrays veya belirtilen bir değerle valarray's öğesi türünde veya valarray tarafından belirtilen değere bölerek bir valarray ayırma ayırma kalan alır.|
|[operator &](../standard-library/valarray-operators.md#op_amp)|Bit düzeyinde edinir **ve** veya bir valarray ile öğe türü belirtilen değeri arasında iki eşit boyutta valarrays öğelere karşılık gelir.|
|[operator & &](../standard-library/valarray-operators.md#op_amp_amp)|Mantıksal edinir **ve** bir valarray ve valarray's öğe türü belirtilen değeri veya iki eşit boyutta valarrays karşılık gelen öğeleri arasında.|
|[operator >](../standard-library/valarray-operators.md#op_gt)|Bir valarray öğelerini eşit boyutta bir valarray veya bir valarray tüm öğeleri sıfırdan büyük veya valarray's öğe türünün belirtilen değerden daha az olup öğelerini büyük olup olmadığını sınar.|
|[operator>=](../standard-library/valarray-operators.md#op_gt_eq)|Bir valarray öğelerini değerinden büyük veya eşit boyutta bir valarray veya olup bir valarray tüm öğeleri daha büyük veya eşit veya daha az veya belirtilen değere eşit öğelerini eşit olup olmadığını sınar.|
|[İşleç >>](../standard-library/valarray-operators.md#op_gt_gt)|Valarray belirtilen sayıda konumlar veya ikinci valarray tarafından belirtilen bir element-wise miktar, her bir öğe için BITS sağa kaydırır.|
|[operator <](../standard-library/valarray-operators.md#op_lt)|Bir valarray öğelerini eşit boyutta bir valarray veya bir valarray tüm öğeleri büyük ya da belirtilen değerden daha az olup öğelerini değerinden olup olmadığını sınar.|
|[operator < =](../standard-library/valarray-operators.md#op_lt_eq)|Bir valarray öğelerini küçük veya buna eşit boyutta bir valarray öğelerini eşit olup olmadığına veya bir valarray tüm öğeleri daha büyük veya eşit veya daha az veya belirtilen değere eşit olup olmadığını sınar.|
|[işleç <<](../standard-library/valarray-operators.md#op_lt_lt)|Valarray belirtilen sayıda konumlar veya ikinci valarray tarafından belirtilen bir element-wise miktar, her bir öğe için BITS Sola kaydırır.|
|[işleç *](../standard-library/valarray-operators.md#op_star)|İki eşit boyutta valarrays ya da, ilgili öğeler arasında element-wise ürün edinir valarray valarray's öğe türü belirtilen değeri arasında.|
|[operator +](../standard-library/valarray-operators.md#op_add)|İki eşit boyutta valarrays ya da, ilgili öğeler arasında element-wise toplam alacağı valarray valarray's öğe türü belirtilen değeri arasında.|
|[operator-](../standard-library/valarray-operators.md#operator-)|Karşılık gelen öğeleri iki eşit boyutta valarrays veya, element-wise birbirinden edinir valarray valarray's öğe türü belirtilen değeri arasında.|
|[operator /](../standard-library/valarray-operators.md#op_div)|İki eşit boyutta valarrays ya da, ilgili öğeler arasında element-wise sayının edinir valarray valarray's öğe türü belirtilen değeri arasında.|
|[operator==](../standard-library/valarray-operators.md#op_eq_eq)|İki eşit boyutta valarrays karşılık gelen öğelerini eşittir veya bir valarray tüm öğeleri olup olup testleri valarray's öğe türünün belirtilen değere eşit.|
|[operator ^](../standard-library/valarray-operators.md#op_xor)|Bit düzeyinde özel edinir `OR` veya bir valarray ile öğe türü belirtilen değeri arasında iki eşit boyutta valarrays öğelere karşılık gelir.|
|[operator&#124;](../standard-library/valarray-operators.md#op_or)|Bit düzeyinde edinir `OR` veya bir valarray ile öğe türü belirtilen değeri arasında iki eşit boyutta valarrays öğelere karşılık gelir.|
|[operator&#124;&#124;](../standard-library/valarray-operators.md#op_lor)|Mantıksal edinir `OR` bir valarray ve valarray's öğe türü belirtilen değeri veya iki eşit boyutta valarrays karşılık gelen öğeleri arasında.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[gslice Sınıfı](../standard-library/gslice-class.md)|Çok boyutlu bir valarray dilimleri tanımlamak için kullanılan valarray için yardımcı sınıfı.|
|[gslice_array Sınıfı](../standard-library/gslice-array-class.md)|Bir valarray genel dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak genel dilim nesneleri destekleyen bir yardımcı, iç Şablon sınıfı.|
|[indirect_array Sınıfı](../standard-library/indirect-array-class.md)|Bir alt kümesini üst valarray dizinlerini belirterek alt diziler arasındaki işlemleri sağlayarak valarrays kümeleridir destekler nesneleri tanımlanmış bir yardımcı, iç Şablon sınıfı.|
|[mask_array Sınıfı](../standard-library/mask-array-class.md)|Üst valarrays kümeleridir destekler nesneleri alt diziler arasındaki işlemleri sağlayarak bir Boolean ifadesiyle belirtilen bir yardımcı, iç Şablon sınıfı.|
|[slice Sınıfı](../standard-library/slice-class.md)|Tek boyutlu, vektör benzeri bir valarray kümelerine tanımlamak için kullanılan valarray için yardımcı sınıfı.|
|[slice_array Sınıfı](../standard-library/slice-array-class.md)|Bir valarray dilim tarafından tanımlanan alt diziler arasındaki işlemleri sağlayarak dilim nesneleri destekleyen bir iç, yardımcı şablonu sınıfı.|
|[valarray Sınıfı](../standard-library/valarray-class.md)|Şablon sınıfı türündeki öğeler bir dizi denetimleri bir nesneyi tanımlayan **türü** , bir dizi olarak saklanır ve hesaplama performans için en iyi duruma getirilmiş hızlı matematik işlemlerini gerçekleştirmek için tasarlanmıştır.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[valarray\<bool > sınıfı](../standard-library/valarray-bool-class.md)|Şablon sınıfı valarray özelleştirilmiş bir sürümünü\<**türü**> türündeki öğeler için `bool`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
