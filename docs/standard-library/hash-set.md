---
title: '&lt;hash_set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <hash_set>
- std::<hash_set>
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
ms.openlocfilehash: ba7716c1c84e8a74495a67f10a78eeaad2a6c3d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159285"
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
