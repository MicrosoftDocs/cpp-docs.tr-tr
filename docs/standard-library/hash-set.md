---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 909944726124a6a3a87ba60ea790945d67ad17a9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Bu üst kullanılmıyor. Alternatif [< unordered_set >](../standard-library/unordered-set.md).

Kapsayıcı şablon sınıfları hash_set ve hash_multiset ve bunların destekleyen şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <hash_set>

```

## <a name="remarks"></a>Açıklamalar

### <a name="operators"></a>İşleçler

|Hash_set sürüm|Hash_multiset sürüm|Açıklama|
|-----------------------|----------------------------|-----------------|
|[operator! = (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator! = (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Testleri işlecinin sol tarafındaki hash_set veya hash_multiset nesnesi sağ tarafında hash_set veya hash_multiset nesnesine eşit değil.|
|[operator == (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator == (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Hash_set veya hash_multiset nesne işlecinin sol tarafındaki sağ tarafında hash_set veya hash_multiset nesnesine eşitse testleri.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_set sürüm|Hash_multiset sürüm|Açıklama|
|-----------------------|----------------------------|-----------------|
|[Swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[Swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|İki hash_sets veya hash_multisets öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](../standard-library/hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcıları tarafından kullanılan bir nesneyi tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak **nitelikler** sıralamak ve içerdikleri öğeleri karma parametre nesnesi.|
|[hash_set Sınıfı](../standard-library/hash-set-class.md)|Hızlı alınması bulunan öğeleri değerlerini benzersiz ve anahtar değerleri olarak hizmet veren bir koleksiyon verileri ve depolama için kullanılır.|
|[hash_multiset Sınıfı](../standard-library/hash-multiset-class.md)|Hızlı alınması bulunan öğeleri değerlerini benzersiz ve anahtar değerleri olarak hizmet veren bir koleksiyon verileri ve depolama için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
