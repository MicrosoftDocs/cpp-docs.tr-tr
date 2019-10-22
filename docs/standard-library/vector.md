---
title: '&lt;vector &gt;'
ms.date: 11/04/2016
f1_keywords:
- <vector>
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
ms.openlocfilehash: 19068de41cfdcb17ae624858c137bf624851479f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72684066"
---
# <a name="ltvectorgt"></a>&lt;vector &gt;

Kapsayıcı sınıfı şablonu vektörünü ve çeşitli destekleyici şablonları tanımlar.

@No__t_0, doğrusal bir dizideki belirli bir türün öğelerini düzenleyen bir kapsayıcıdır. Bu, herhangi bir öğeye ve dizi üzerinde dinamik ekleme ve kaldırma işlemleri için hızlı rastgele erişim sağlar. @No__t_0, rastgele erişim performansı Premium olduğunda bir sıra için tercih edilen kapsayıcıdır.

> [!NOTE]
> @No__t_0vector > kitaplığı `#include <initializer_list>` ifadesini de kullanır.

@No__t_0 sınıfı hakkında daha fazla bilgi için bkz. [Vector sınıfı](../standard-library/vector-class.md). Özelleşme `vector<bool>` hakkında daha fazla bilgi için bkz. [vector \<bool > sınıfı](../standard-library/vector-bool-class.md).

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

*Tür* \
Vektörde depolanan veri türü için şablon parametresi.

*Ayırıcı* \
Depolanan ayırıcı nesnesinin bellek ayırmayı ve ayırmayı kaldırma işleminden sorumlu şablon parametresi.

*sol* \
Karşılaştırma işleminde ilk (sol) vektör

*sağ* \
Karşılaştırma işleminde ikinci (sağ) vektör.

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işlecinde! =](../standard-library/vector-operators.md#op_neq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/vector-operators.md#op_lt)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesinden küçük olup olmadığını sınar.|
|[işleç \< =](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit veya ondan küçük olup olmadığını test eder.|
|[işleç = =](../standard-library/vector-operators.md#op_eq_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç >](../standard-library/vector-operators.md#op_gt)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesinden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesinin, sağ taraftaki vektör nesnesine eşit veya ondan büyük olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[vector Sınıfı](../standard-library/vector-class.md)|Belirli bir türün öğelerini doğrusal bir düzenlemede düzenleyen ve herhangi bir öğeye hızlı rastgele erişime izin veren dizi kapsayıcılarının sınıf şablonu.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|hash|Vektörün karmasını döndürür.|
|[vektör \<bool > sınıfı](../standard-library/vector-bool-class.md)|Özelleştirme tarafından kullanılan temel tür için bir ayırıcıyla `bool` türündeki öğeler için sınıf şablonu vektörünün tam özelleştirmesi.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<vector >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
