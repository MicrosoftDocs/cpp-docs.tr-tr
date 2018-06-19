---
title: '&lt;vektör&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fc8fb21afe1f024e4e5418d3cc706f654946de6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857642"
---
# <a name="ltvectorgt"></a>&lt;vektör&gt;

Kapsayıcı Şablon sınıfı vektör ve çeşitli destekleyici şablonları tanımlar.

`vector` Doğrusal bir sıra içinde belirli bir türde öğeleri düzenler bir kapsayıcıdır. Öğesini ve dinamik ekleme ve kaldırma işlemleri için ve serisinden hızlı rastgele erişim sağlar. `vector` Rasgele erişim performansı üst düzey olduğunda tercih edilen sıralı bir kapsayıcısıdır.

Sınıfı hakkında daha fazla bilgi için `vector`, bkz: [vector sınıfı](../standard-library/vector-class.md). Özelleştirme hakkında bilgi için `vector<bool>`, bkz: [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md).

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

Şablon parametresi vektörü depolanan veri türünün yazın.

Bellek ayırma ve ayırmayı kaldırma sorumlu saklı ayırıcısı nesnesi için şablon parametresi ayırıcısı.

`left` Bir karşılaştırma işlemi ilk (soldaki) vektörü

`right` Bir karşılaştırma işlemi ikinci (sağdaki) vektörü.

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci! =](../standard-library/vector-operators.md#op_neq)|Testleri işlecinin sol tarafındaki vektör nesnesi sağ tarafında vektör nesnesine eşit değil.|
|[operator <](../standard-library/vector-operators.md#op_lt)|Vektör nesnesi işlecinin sol tarafındaki sağ tarafında vektör nesnesi küçükse testleri.|
|[işleci\<=](../standard-library/vector-operators.md#op_gt_eq)|Vektör işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında vektör nesnesi eşit veya daha az olur.|
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|Vektör nesnesi işlecinin sol tarafındaki sağ tarafında vektör nesnesine eşitse testleri.|
|[operator >](../standard-library/vector-operators.md#op_gt)|Testleri işlecinin sol tarafındaki vektör nesnesi sağ tarafında vektör nesnesi değerinden daha büyük.|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|Vektör işlecinin sol tarafındaki sağ tarafında vektör nesnesine eşit veya daha büyük bir nesneyse testleri.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[vector Sınıfı](../standard-library/vector-class.md)|Doğrusal bir düzenleme içinde belirli bir türde öğelerini düzenlemek ve herhangi bir öğeye hızlı rastgele erişim izin veren dizisi kapsayıcıların bir şablon sınıfı.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[vektör\<bool > sınıfı](../standard-library/vector-bool-class.md)|Şablon sınıfı vektör türündeki öğeler için tam uzmanlaşması `bool` uzmanlık tarafından kullanılan temel alınan türü için bir ayırıcı ile.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<vektör >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
