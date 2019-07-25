---
title: '&lt;valarray&gt;'
ms.date: 11/04/2016
f1_keywords:
- <valarray>
helpviewer_keywords:
- valarray header
ms.assetid: 30835415-21c1-4801-8f24-6bbef7dd8ecd
ms.openlocfilehash: c18b72017e4999e377bf8575f624f8fdda5b0caf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448350"
---
# <a name="ltvalarraygt"></a>&lt;valarray&gt;

Şablon sınıfı valarray ve birçok destekleyici şablon sınıfı ve işlevi tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<valarray >

**Ad alanı:** std

> [!NOTE]
> \<Valarray > Kitaplığı ' #include < initializer_list > ' ifadesini kullanır.

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfları ve işlevleri, gelişmiş performans konusunda olağan dışı Enlem ile izin verilir. Özellikle, tür `valarray<T1>` döndüren herhangi bir işlev bazı T2 türünde bir nesne döndürebilir. Bu durumda, türünde `valarray<T2>` bir veya daha fazla bağımsız değişken kabul eden herhangi bir işlev, bu bağımsız değişkenlerin rastgele birleşimlerini kabul eden aşırı yüklemeleri içermelidir, her biri T2 türünde bir bağımsız değişkenle değiştirilmiştir.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[mutlak](../standard-library/valarray-functions.md#abs)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin mutlak değerine eşit olan bir valarray döndürür.|
|[acos](../standard-library/valarray-functions.md#acos)|, Bir giriş valarray öğeleri üzerinde çalışır, öğeleri girdi valarray öğelerinin Arkkosinüs değerine eşit olan bir valarray döndürür.|
|[asin](../standard-library/valarray-functions.md#asin)|, Bir giriş valarray öğeleri üzerinde çalışır, öğeleri girdi valarray öğelerinin arksinüsünü eşit olan bir valarray döndürür.|
|[atan](../standard-library/valarray-functions.md#atan)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin arktanjant değerinin asıl değerine eşit olan bir valarray döndürür.|
|[atan2](../standard-library/valarray-functions.md#atan2)|Öğeleri, valarışın sabitlerinin ve öğelerinin bir birleşimiyle belirtilen Kartezyen bileşenlerinin ark birleşimine eşit olan bir valarray döndürür.|
|[başladı](../standard-library/valarray-functions.md#begin)||
|[cos](../standard-library/valarray-functions.md#cos)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin kosinüs değerine eşit olan bir valarray döndürür.|
|[Cosh](../standard-library/valarray-functions.md#cosh)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin hiperbolik kosinüs değerine eşit olan bir valarray döndürür.|
|[erer](../standard-library/valarray-functions.md#end)||
|[exp](../standard-library/valarray-functions.md#exp)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin doğal üslerinin değerine eşit olan bir valarray döndürür.|
|[log](../standard-library/valarray-functions.md#log)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin doğal logaritmasına eşit olan bir valarray döndürür.|
|[log10](../standard-library/valarray-functions.md#log10)|, Bir giriş valarray öğeleri üzerinde çalışır; bu bir valarray, öğeleri 10 tabanında veya giriş valarray öğelerinin ortak logaritmasına eşit olan bir döndürür.|
|[POW](../standard-library/valarray-functions.md#pow)|Giriş valarışın ve sabitlerin öğeleri üzerinde çalışır, öğeleri bir giriş valarray öğeleri tarafından belirtilen bir tabana veya bir giriş valarray öğeleri tarafından belirtilen bir sabite ya da bir valarray sabit.|
|[sin](../standard-library/valarray-functions.md#sin)|, Bir giriş valarray öğeleri üzerinde çalışır, öğeleri girdi valarray öğelerinin Sinüs değerine eşit olan bir valarray döndürür.|
|[sinh](../standard-library/valarray-functions.md#sinh)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin hiperbolik sinüsünü eşit olan bir valarray döndürür.|
|[sqrt](../standard-library/valarray-functions.md#sqrt)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin kare köküne eşit olan bir valarray döndürür.|
|[Kur](../standard-library/valarray-functions.md#swap)||
|[Başlangıçtan](../standard-library/valarray-functions.md#tan)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin tanjantını eşit olan bir valarray döndürür.|
|[tanh](../standard-library/valarray-functions.md#tanh)|, Bir giriş valarray öğeleri üzerinde çalışır ve öğeleri, giriş valarray öğelerinin hiperbolik tanjantisine eşit olan bir valarray döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/valarray-operators.md#op_neq)|Eşit olarak boyutlandırılmış iki valarışın öğesine karşılık gelen öğelerin eşit olup olmadığını veya bir valarray öğesinin tüm öğelerinin valarray öğesi türünün belirtilen bir değeri ile eşit olup olmadığını sınar.|
|[operator%](../standard-library/valarray-operators.md#op_mod)|İki eşit ölçekli valarışın karşılık gelen öğelerin bölünmesinin veya bir valarray 'in belirtilen bir değeri valarray öğesinin bir valarray tarafından bölünmesinin geri kalanını edinir.|
|[işleç &](../standard-library/valarray-operators.md#op_amp)|İki eşit ölçekli `AND` valarışın karşılık gelen öğeler arasında bit düzeyinde veya bir valarray ile belirtilen bir değer olan öğe türünü alır.|
|[işleç & &](../standard-library/valarray-operators.md#op_amp_amp)|İki eşit ölçekli `AND` valarışın karşılık gelen öğeleri veya bir valarray ile valarray öğesinin öğe türünün belirtilen değeri arasında mantıksal değer edinir.|
|[işleç >](../standard-library/valarray-operators.md#op_gt)|Bir valarray öğelerinin eşit boyutlu bir valarray öğelerinden büyük olup olmadığını veya valarray tüm öğelerinin valarray öğesinin belirtilen değerinden büyük veya küçük olup olmadığını sınar.|
|[operator>=](../standard-library/valarray-operators.md#op_gt_eq)|Bir valarray öğelerinin eşit boyutlu bir valarray öğesinden büyük veya ona eşit olup olmadığını ya da bir valarray öğelerinin, belirtilen bir değerden büyük veya ona eşit veya ondan büyük veya ona eşit olup olmadığını sınar.|
|[işleç > >](../standard-library/valarray-operators.md#op_gt_gt)|Bir valarray öğesinin her öğesi için bitleri, belirtilen sayıda konum veya bir ikinci valarray tarafından belirtilen öğe temelinde bir miktar ile sağa kaydırır.|
|[işleç <](../standard-library/valarray-operators.md#op_lt)|Bir valarray öğelerinin eşit boyutlu bir valarray öğelerinden daha küçük olup olmadığını veya bir valarray tüm öğelerinin belirtilen değerden büyük veya küçük olup olmadığını sınar.|
|[işleç < =](../standard-library/valarray-operators.md#op_lt_eq)|Bir valarray öğelerinin eşit boyutlu bir valarray öğesinden küçük veya ona eşit olup olmadığını ya da bir valarray öğelerinin, belirtilen bir değerden büyük veya ona eşit veya ondan daha büyük veya ona eşit olup olmadığını sınar.|
|[işleç < <](../standard-library/valarray-operators.md#op_lt_lt)|Sol, bir valarray öğesinin her öğesi için bitleri belirtilen sayıda konum veya bir ikinci valarray tarafından belirtilen öğe temelinde bir sayı ile kaydırır.|
|[işlecinde](../standard-library/valarray-operators.md#op_star)|İki eşit ölçekli valarışın karşılık gelen öğeler arasında ya da valarray ' nin belirtilen valarray öğesi türünün belirtilen değeri arasındaki öğe odaklı ürünü edinir.|
|[işleç +](../standard-library/valarray-operators.md#op_add)|İki eşit ölçekli valarışın karşılık gelen öğeler arasındaki öğe temelinde toplamı alır veya bir valarray 'in belirtilen bir değeri olan valarray öğesinin öğe türü.|
|[işlecinde](../standard-library/valarray-operators.md#operator-)|İki eşit ölçekli valarışın karşılık gelen öğeler arasında öğe temelinde fark elde eder veya bir valarray 'in belirtilen bir değeri olan valarray öğesinin öğe türünü alır.|
|[işlecinde](../standard-library/valarray-operators.md#op_div)|İki eşit ölçekli valarışın karşılık gelen öğeler arasında veya valarray öğesinin belirtilen bir değeri arasında öğe temelinde bölüm edinir.|
|[operator==](../standard-library/valarray-operators.md#op_eq_eq)|Eşit olarak boyutlandırılmış iki valarışın öğesine karşılık gelen öğelerin eşit olup olmadığını veya bir valarray öğesinin tüm öğelerinin valarray öğesi türünün belirtilen bir değerine eşit olup olmadığını sınar.|
|[işleç ^](../standard-library/valarray-operators.md#op_xor)|İki eşit ölçekli valarışın karşılık gelen öğeler arasında bit düzeyinde dışlamalı `OR` veya bir valarray ile belirtilen öğe türü değeri arasında bir değer alır.|
|[operator&#124;](../standard-library/valarray-operators.md#op_or)|İki eşit ölçekli `OR` valarışın karşılık gelen öğeler arasında bit düzeyinde veya bir valarray ile belirtilen bir değer olan öğe türünü alır.|
|[operator&#124;&#124;](../standard-library/valarray-operators.md#op_lor)|İki eşit ölçekli `OR` valarışın karşılık gelen öğeleri veya bir valarray ile valarray öğesinin öğe türünün belirtilen değeri arasında mantıksal değer edinir.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[gslice Sınıfı](../standard-library/gslice-class.md)|Bir valarray 'ın çok boyutlu dilimlerini tanımlamak için kullanılan valarray için yardımcı program sınıfı.|
|[gslice_array Sınıfı](../standard-library/gslice-array-class.md)|Bir valarray genel dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak genel dilim nesnelerini destekleyen iç, yardımcı şablon sınıfı.|
|[indirect_array Sınıfı](../standard-library/indirect-array-class.md)|Bir üst valarray dizinlerinin alt kümesini belirterek tanımlanan alt küme dizileri arasında işlemler sağlayarak, valarışın alt kümeleri olan nesneleri destekleyen iç, yardımcı şablon sınıfı.|
|[mask_array Sınıfı](../standard-library/mask-array-class.md)|Alt küme dizileri arasında işlemler sağlayarak bir Boolean ifadesiyle belirtilen üst valarışın alt kümeleri olan nesneleri destekleyen dahili, yardımcı şablon sınıfı.|
|[slice Sınıfı](../standard-library/slice-class.md)|Bir valarray 'ın vektör benzeri alt kümelerini tanımlamak için kullanılan valarray için yardımcı program sınıfı.|
|[slice_array Sınıfı](../standard-library/slice-array-class.md)|Bir valarray dilimi tarafından tanımlanan alt küme dizileri arasında işlemler sağlayarak dilim nesnelerini destekleyen dahili, yardımcı şablon sınıfı.|
|[valarray Sınıfı](../standard-library/valarray-class.md)|Şablon sınıfı, bir dizi olarak depolanan ve yüksek hızlı matematik işlemlerini gerçekleştirmek için `Type` tasarlanan ve hesaplama performansı için iyileştirilmiş bir öğe dizisini denetleyen bir nesneyi tanımlar.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[valarray\<bool > sınıfı](../standard-library/valarray-bool-class.md)|Valarray\<**Type**şablon sınıfının özelleşmiş bir sürümü **bool**türündeki öğelere >.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
