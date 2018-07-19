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
ms.openlocfilehash: caae1a52c36c5d21e55e90a821b280f2face7ede
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959780"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Bu üst bilgi kullanılmıyor. Alternatif [ \<unordered_map >](unordered-map.md).

Kapsayıcı şablon sınıfları hash_map ve hash_multimap ve kendi destek şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

> #<a name="include-hashmap"></a>< hash_map > Ekle

### <a name="operators"></a>İşleçler

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesne işlecin sağ tarafındaki hash_map veya hash_multimap nesneye eşit olup olmadığını sınar.|
|[işleç == (hash_map)](hash-map-operators.md#op_eq_eq)|[işleç == (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|İşlecin sol tarafındaki hash_map veya hash_multimap nesnesinin işlecin sağ tarafındaki hash_map veya hash_multimap nesneye eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_map sürümü|Hash_multimap sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[Swap (hash_map)](hash-map-class.md#swap)|[Swap (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini birbiriyle değiştirir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcılar tarafından kullanılabilen bir nesne tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak `Traits` sipariş ve içerdikleri öğelerin karma parametre nesnesi.|
|[value_compare Sınıfı](value-compare-class.md)|Hash_map kendi göreli sıralarını belirlemek için kendi anahtarını değerlerini karşılaştırarak bir hash_map öğelerini karşılaştıran bir işlev nesnesi sağlar.|
|[hash_map Sınıfı](hash-map-class.md)|Her bir öğenin değeri benzersiz olan sıralama anahtarına sahip olduğu bir çift olan bir koleksiyonu ve ilişkili veriler bir değer verileri hızlı alma ve depolama için kullanılır.|
|[hash_multimap Sınıfı](hash-multimap-class.md)|Her bir öğenin değerini benzersiz olması gerekmez sıralama anahtarına sahip olduğu bir çift olan bir koleksiyonu ve ilişkili veriler bir değer verileri hızlı alma ve depolama için kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](cpp-standard-library-header-files.md)
[güvenliği C++ Standart kitaplığında iş parçacığı](thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)
