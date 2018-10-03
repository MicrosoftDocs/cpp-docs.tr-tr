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
ms.openlocfilehash: f9a94fbf8ae46c2abf65fc0229bbb2faa54d695f
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235029"
---
# <a name="ltvectorgt"></a>&lt;vektör&gt;

Kapsayıcı Şablon sınıfı vektör ve çeşitli destek şablonları tanımlar.

`vector` Doğrusal bir sırada belirli bir türden öğeler düzenleyen bir kapsayıcıdır. Bu öğe ve dinamik ekleme ve çıkarma için ve serisinden hızlı rastgele erişim sağlar. `vector` Rastgele erişimli performans bir premium olduğunda tercih edilen bir dizi kapsayıcısıdır.

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

*Türü*<br/>
Şablon parametresi için vektör içinde depolanan verinin türü.

*Ayırıcı*<br/>
Şablon parametresi için bellek ayırmayı ve ayırmayı kaldırma için sorumlu saklı ayırıcı nesnesini.

*Sol*<br/>
Bir karşılaştırma işlemi ilk (soldaki) vektörü

*sağ*<br/>
Bir karşılaştırma işleminde ikinci (sağdaki) vektör.

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci! =](../standard-library/vector-operators.md#op_neq)|İşlecin sol tarafındaki vektör nesnesi işlecin sağ tarafındaki vektör nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/vector-operators.md#op_lt)|İşlecin sol tarafındaki vektör nesnesi işlecin sağ tarafındaki vektör nesneden küçük olup olmadığını sınar.|
|[İşleci\<=](../standard-library/vector-operators.md#op_gt_eq)|İşlecinin sol tarafında vektör nesnesi küçük olup olmadığını sınar vektör nesnesine eşit veya işlecin sağ tarafındaki.|
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|İşlecin sol tarafındaki vektör nesnesinin işlecin sağ tarafındaki vektör nesnesine eşit olup olmadığını sınar.|
|[operator >](../standard-library/vector-operators.md#op_gt)|İşlecin sol tarafındaki vektör nesnesi vektör nesnesi işlecin sağ tarafındaki büyük olup olmadığını sınar.|
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|İşlecin sol tarafındaki vektör nesnesi büyük veya işlecin sağ tarafındaki vektör nesnesine eşit olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[vector Sınıfı](../standard-library/vector-class.md)|Öğeleri belirli bir türden doğrusal bir düzende düzenlemek ve herhangi bir öğeye hızlı rastgele erişim izin veren bir dizi kapsayıcılarının bir şablon sınıfı.|

### <a name="specializations"></a>Uzmanlıklar

|||
|-|-|
|[vektör\<bool > sınıfı](../standard-library/vector-bool-class.md)|Şablon sınıfı vektör türü öğeler için tam özelleştirmesi `bool` uzmanlık tarafından kullanılan temel alınan türü için bir ayırıcı ile.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<vektör >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
