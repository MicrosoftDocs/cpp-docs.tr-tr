---
description: 'Hakkında daha fazla bilgi edinin: &lt; hash_set&gt;'
title: '&lt;hash_set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <hash_set>
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
ms.openlocfilehash: aec05414d11bd5312febf4dd61b71db1b3f04452
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98125967"
---
# <a name="lthash_setgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Bu üst bilgi artık kullanılmıyor. Alternatif, [>unordered_set<](../standard-library/unordered-set.md).

Kapsayıcı sınıfı şablonları hash_set ve hash_multiset ve destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Syntax

```cpp
#include <hash_set>
```

## <a name="remarks"></a>Açıklamalar

### <a name="operators"></a>İşleçler

|Hash_set sürümü|Hash_multiset sürümü|Description|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[işleç! = (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|İşlecin sol tarafındaki hash_set veya hash_multiset nesnesinin sağ taraftaki hash_set veya hash_multiset nesnesine eşit olmadığını sınar.|
|[işleç = = (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[işleç = = (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|İşlecin sol tarafındaki hash_set veya hash_multiset nesnesinin sağ taraftaki hash_set veya hash_multiset nesnesine eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_set sürümü|Hash_multiset sürümü|Description|
|-----------------------|----------------------------|-----------------|
|[takas (hash_set)](../standard-library/hash-set-functions.md#swap)|[takas (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|İki hash_sets veya hash_multisets öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[hash_compare sınıfı](../standard-library/hash-compare-class.md)|Hash_map, hash_multimap, hash_set veya hash_multiset gibi karma ilişkilendirilebilir kapsayıcılardan herhangi biri tarafından kullanılabilecek bir nesneyi `Traits` , içerdikleri öğeleri sıralamak ve sağlaması için varsayılan bir parametre nesnesi olarak tanımlar.|
|[hash_set Sınıfı](../standard-library/hash-set-class.md)|İçerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.|
|[hash_multiset sınıfı](../standard-library/hash-multiset-class.md)|İçerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
