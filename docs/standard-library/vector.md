---
title: '&lt;vektör&gt;'
ms.date: 11/04/2016
f1_keywords:
- <vector>
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
ms.openlocfilehash: 5992e368031b59c9b892167b135fa30a870c73f9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448062"
---
# <a name="ltvectorgt"></a>&lt;vektör&gt;

Kapsayıcı şablon sınıfı vektörünü ve çeşitli destekleyici şablonları tanımlar.

, `vector` Belirli bir türün öğelerini doğrusal bir dizide düzenleyen bir kapsayıcıdır. Bu, herhangi bir öğeye ve dizi üzerinde dinamik ekleme ve kaldırma işlemleri için hızlı rastgele erişim sağlar. , `vector` Rastgele erişim performansı Premium olduğunda bir sıra için tercih edilen kapsayıcıdır.

> [!NOTE]
> Vektör > kitaplığı, `#include <initializer_list>` ifadesini de kullanır. \<

Sınıfı `vector`hakkında daha fazla bilgi için bkz. [Vector sınıfı](../standard-library/vector-class.md). Özelleştirme `vector<bool>`hakkında daha fazla bilgi için bkz [.\<vektör bool > sınıfı](../standard-library/vector-bool-class.md).

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

|||
|-|-|
|[işlecinde! =](../standard-library/vector-operators.md#op_neq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/vector-operators.md#op_lt)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesinden küçük olup olmadığını sınar.|
|[işlecinde\<=](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit veya ondan küçük olup olmadığını test eder.|
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç >](../standard-library/vector-operators.md#op_gt)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesinden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit veya ondan büyük olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[vector Sınıfı](../standard-library/vector-class.md)|Bir doğrusal düzenlemede belirli bir türün öğelerini düzenleyen ve herhangi bir öğeye hızlı rastgele erişime izin veren dizi kapsayıcılarının şablon sınıfı.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[yla]()||
|[vektör\<bool > sınıfı](../standard-library/vector-bool-class.md)|Özelleştirme tarafından kullanılan temel tür için bir ayırıcıyla tür `bool` öğeleri için şablon sınıfı vektörünün tam özelleştirmesi.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<vektör >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
