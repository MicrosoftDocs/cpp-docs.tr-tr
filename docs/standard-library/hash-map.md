---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0e3948e8697825af6cdd785117647943b33bac0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Bu üst kullanılmıyor. Alternatif [ \<unordered_map >](unordered-map.md).

Kapsayıcı şablon sınıfları hash_map ve hash_multimap ve bunların destekleyen şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

> #<a name="include-hashmap"></a>< hash_map > içerir

### <a name="operators"></a>İşleçler

|Hash_map sürüm|Hash_multimap sürüm|Açıklama|
|-----------------------|----------------------------|-----------------|
|[operator! = (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Testleri işlecinin sol tarafındaki hash_map veya hash_multimap nesnesi sağ tarafında hash_map veya hash_multimap nesnesine eşit değil.|
|[operator == (hash_map)](hash-map-operators.md#op_eq_eq)|[operator == (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Hash_map veya hash_multimap nesne işlecinin sol tarafındaki sağ tarafında hash_map veya hash_multimap nesnesine eşitse testleri.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_map sürüm|Hash_multimap sürüm|Açıklama|
|-----------------------|----------------------------|-----------------|
|[Swap (hash_map)](hash-map-class.md#swap)|[Swap (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcıları tarafından kullanılan bir nesneyi tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak **nitelikler** sıralamak ve içerdikleri öğeleri karma parametre nesnesi.|
|[value_compare Sınıfı](value-compare-class.md)|Hash_map içindeki göreli sıralarına belirlemek için kendi anahtarları değerlerinin karşılaştırılmasıyla bir hash_map öğelerini karşılaştırabilirsiniz bir işlev nesnesi sağlar.|
|[hash_map Sınıfı](hash-map-class.md)|Her öğe değeri benzersiz olan sıralama anahtarı olan bir çift olduğu bir koleksiyon ve ilişkili veriler bir değer verileri hızlı alınmasını ve depolama için kullanılır.|
|[hash_multimap Sınıfı](hash-multimap-class.md)|Her öğe değeri benzersiz olması gerekmez sıralama anahtarı olan bir çift olduğu bir koleksiyon ve ilişkili veriler bir değer verileri hızlı alınmasını ve depolama için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](cpp-standard-library-header-files.md)
[güvenliği C++ Standart kitaplığında iş parçacığı](thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
