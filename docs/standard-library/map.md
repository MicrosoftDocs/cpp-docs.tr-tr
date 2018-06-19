---
title: '&lt;Harita&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac523342cc175721b9c1ef33a3d8ac4cad83033b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853371"
---
# <a name="ltmapgt"></a>&lt;eşleme&gt;

Kapsayıcı şablon sınıfları harita ve multimap ve bunların destekleyen şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <map>

```

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Harita sürümü|Multimap sürüm|Açıklama|
|-----------------|----------------------|-----------------|
|[operator! = (map)](../standard-library/map-operators.md#op_neq)|[operator! = (multimap)](../standard-library/map-operators.md#op_neq)|Testleri işlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesine eşit değil.|
|[operator < (map)](../standard-library/map-operators.md#op_eq_eq)|[operator < (multimap)](../standard-library/map-operators.md#op_eq_eq)|Testleri işlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesi'dan küçük.|
|[operator < = (map)](../standard-library/map-operators.md#op_lt)|[İşleç\<= (multimap)](../standard-library/map-operators.md#op_lt)|Harita veya multimap nesne işlecinin sol tarafındaki harita veya sağ tarafında multimap nesneye eşit veya daha az ise testleri.|
|[operator == (map)](../standard-library/map-operators.md#op_eq_eq)|[operator == (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|İşlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesine eşitse testleri.|
|[operator > (map)](../standard-library/map-operators.md#op_gt)|[operator > (multimap)](../standard-library/map-operators.md#op_gt_multimap)|Testleri işlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesi değerinden daha büyük.|
|[operator > = (map)](../standard-library/map-operators.md#op_gt_eq)|[operator > = (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|Harita veya multimap nesne işlecinin sol tarafındaki sağ tarafında harita veya birden çok eşleme nesnesine eşit veya daha büyük ise testleri.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Harita sürümü|Multimap sürüm|Açıklama|
|-----------------|----------------------|-----------------|
|[Swap (map)](../standard-library/map-functions.md#swap)|[Swap (multimap)](../standard-library/map-functions.md#swap_multimap)|İki eşlemeleri veya multimaps öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[value_compare Sınıfı](../standard-library/value-compare-class-map.md)|Bir harita öğelerini göreli sıralarına eşlemesindeki belirlemek için kendi anahtarları değerleri karşılaştırarak karşılaştırabilirsiniz bir işlev nesnesi sağlar.|
|[map Sınıfı](../standard-library/map-class.md)|Depolama ve alma verilerini öğelerin her biri benzersiz bir anahtar ile veriler otomatik olarak sıralanır sahip bir koleksiyon için kullanılır.|
|[multimap Sınıfı](../standard-library/multimap-class.md)|Depolama ve alma verilerini öğelerin her biri hangi verileri otomatik olarak sıralanır ve anahtarları, benzersiz değerlere sahip olması gerekmez. bir anahtarı olan bir koleksiyon için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
