---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f163ef7d0e5ec05dd0f41c11ea77c558cfef4919
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955712"
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Bu üst bilgi kullanılmıyor. Alternatif [< unordered_set >](../standard-library/unordered-set.md).

Kapsayıcı şablon sınıfları hash_set ve hash_multiset ve kendi destek şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <hash_set>

```

## <a name="remarks"></a>Açıklamalar

### <a name="operators"></a>İşleçler

|Hash_set sürümü|Hash_multiset sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[işleç! = (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|İşlecin sol tarafındaki hash_set veya hash_multiset nesne işlecin sağ tarafındaki hash_set veya hash_multiset nesneye eşit olup olmadığını sınar.|
|[işleç == (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[işleç == (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|İşlecin sol tarafındaki hash_set veya hash_multiset nesnesinin işlecin sağ tarafındaki hash_set veya hash_multiset nesneye eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_set sürümü|Hash_multiset sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[Swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[Swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|İki hash_sets veya hash_multisets öğelerini birbiriyle değiştirir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](../standard-library/hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcılar tarafından kullanılabilen bir nesne tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak `Traits` sipariş ve içerdikleri öğelerin karma parametre nesnesi.|
|[hash_set Sınıfı](../standard-library/hash-set-class.md)|Hızlı, içerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak hizmet verdikleri bir koleksiyondan verilerin alınmasını ve depolama için kullanılır.|
|[hash_multiset Sınıfı](../standard-library/hash-multiset-class.md)|Hızlı, içerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak hizmet verdikleri bir koleksiyondan verilerin alınmasını ve depolama için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
