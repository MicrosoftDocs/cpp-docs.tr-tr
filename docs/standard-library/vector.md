---
description: 'Daha fazla bilgi edinin: &lt; vektör&gt;'
title: '&lt;vektör&gt;'
ms.date: 11/04/2016
f1_keywords:
- <vector>
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
ms.openlocfilehash: 1f787afb00a3f94ba6b5148fe064badbc5d373ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187864"
---
# <a name="ltvectorgt"></a>&lt;vektör&gt;

Kapsayıcı sınıfı şablonu vektörünü ve çeşitli destekleyici şablonları tanımlar.

, `vector` Belirli bir türün öğelerini doğrusal bir dizide düzenleyen bir kapsayıcıdır. Bu, herhangi bir öğeye ve dizi üzerinde dinamik ekleme ve kaldırma işlemleri için hızlı rastgele erişim sağlar. , `vector` Rastgele erişim performansı Premium olduğunda bir sıra için tercih edilen kapsayıcıdır.

> [!NOTE]
> \<vector>Kitaplık, ifadesini de kullanır `#include <initializer_list>` .

Sınıfı hakkında daha fazla bilgi için `vector` bkz. [Vector sınıfı](../standard-library/vector-class.md). Özelleştirme hakkında daha fazla bilgi için `vector<bool>` bkz. [Vector \<bool> sınıfı](../standard-library/vector-bool-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
namespace std {
template <class Type, class Allocator>
class vector;
template <class Allocator>
class vector<bool>;

template <class Allocator>
struct hash<vector<bool, Allocator>>;

// TEMPLATE FUNCTIONS
template <class Type, class Allocator>
bool operator== (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator!= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<(
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator> (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator<= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
bool operator>= (
    const vector<Type, Allocator>& left,
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>
void swap (
    vector<Type, Allocator>& left,
    vector<Type, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Vektörde depolanan veri türü için şablon parametresi.

*Öğe*\
Depolanan ayırıcı nesnesinin bellek ayırmayı ve ayırmayı kaldırma işleminden sorumlu şablon parametresi.

*tarafta*\
Karşılaştırma işleminde ilk (sol) vektör

*Right*\
Karşılaştırma işleminde ikinci (sağ) vektör.

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işlecinde! =](../standard-library/vector-operators.md#op_neq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç<](../standard-library/vector-operators.md#op_lt)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesinden küçük olup olmadığını sınar.|
|[işlecinde\<=](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit veya ondan küçük olup olmadığını test eder.|
|[işleç = =](../standard-library/vector-operators.md#op_eq_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç>](../standard-library/vector-operators.md#op_gt)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesinden büyük olup olmadığını sınar.|
|[işleç>=](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit veya ondan büyük olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[Vector sınıfı](../standard-library/vector-class.md)|Belirli bir türün öğelerini doğrusal bir düzenlemede düzenleyen ve herhangi bir öğeye hızlı rastgele erişime izin veren dizi kapsayıcılarının sınıf şablonu.|

### <a name="specializations"></a>Uzmanlıklar

|Ad|Açıklama|
|-|-|
|hash|Vektörün karmasını döndürür.|
|[Vector \<bool> sınıfı](../standard-library/vector-bool-class.md)|**`bool`** Özelleştirme tarafından kullanılan temel tür için bir ayırıcıyla birlikte türündeki öğeler için sınıf şablonu vektörünün tam özelleştirmesi.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<vector>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
