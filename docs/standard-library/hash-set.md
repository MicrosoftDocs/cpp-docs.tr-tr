---
title: '&lt;hash_set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <hash_set>
- std::<hash_set>
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
ms.openlocfilehash: 559bbff00b8e5204dd4f381abaf9987b4752db48
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452015"
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;

> [!NOTE]
> Bu üst bilgi artık kullanılmıyor. Alternatif, [< unordered_set >](../standard-library/unordered-set.md).

Hash_set ve hash_multiset kapsayıcı şablonu sınıflarını ve bunların destekleyici şablonlarını tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <hash_set>
```

## <a name="remarks"></a>Açıklamalar

### <a name="operators"></a>İşleçler

|Hash_set sürümü|Hash_multiset sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[işleç! = (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[işleç! = (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|İşlecin sol tarafındaki hash_set veya hash_multiset nesnesinin sağ taraftaki hash_set veya hash_multiset nesnesine eşit olup olmadığını sınar.|
|[operator = = (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator = = (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|İşlecin sol tarafındaki hash_set veya hash_multiset nesnesinin sağ taraftaki hash_set veya hash_multiset nesnesine eşit olup olmadığını sınar.|

### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri

|Hash_set sürümü|Hash_multiset sürümü|Açıklama|
|-----------------------|----------------------------|-----------------|
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|İki hash_sets veya hash_multisets öğelerini değiş tokuş eder.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[hash_compare Sınıfı](../standard-library/hash-compare-class.md)|Hash_map, hash_multimap, hash_set veya hash_multiset gibi karma ilişkilendirilebilir kapsayıcılardan herhangi biri tarafından, içerdikleri öğeleri sıralamak ve karma hale getirmek için varsayılan `Traits` bir parametre nesnesi olarak kullanılabilecek bir nesneyi tanımlar.|
|[hash_set Sınıfı](../standard-library/hash-set-class.md)|İçerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.|
|[hash_multiset Sınıfı](../standard-library/hash-multiset-class.md)|İçerdiği öğelerin değerlerinin benzersiz olduğu ve anahtar değerler olarak kullanıldığı bir koleksiyondaki verilerin depolanması ve hızlı bir şekilde alınması için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
