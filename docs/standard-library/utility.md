---
title: '&lt;yardımcı programı&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 318cd86832875f3701c5d164ce9150e6adddb242
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467215"
---
# <a name="ltutilitygt"></a>&lt;yardımcı programı&gt;

C++ standart kitaplık türleri, İşlevler ve oluşturmak ve iki nesne bir oldukları gibi kabul gerektiğinde yararlı olan nesneleri çiftlerini yönetmek üzere Yardım işleçler tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <utility>

```

## <a name="remarks"></a>Açıklamalar

Çiftler, C++ Standart Kitaplığı'nda yaygın olarak kullanılır. Çeşitli işlevleri için dönüş değerleri ve bağımsız olarak hem de olduğu gibi kapsayıcılar için öğe türleri olarak gereklidirler [harita sınıfı](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md). \<Yardımcı programı > tarafından otomatik olarak üst bilgisi dahil \<harita >, anahtar/değer yönetilmesine yardımcı olmak için çifti öğelerini yazın.

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Bir sınıf türü sarmalayan bir `pair` öğesi.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Saran bir sınıf `pair` öğe sayısı.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[İleriye doğru](../standard-library/utility-functions.md#forward)|Başvuru türü korur (ya da `lvalue` veya `rvalue`) tarafından kusursuz iletme engellediği gelen bağımsız değişken.|
|[get](../standard-library/utility-functions.md#get)|Bir öğeyi alır bir işlev bir `pair` nesne.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Türündeki nesneler oluşturmak için kullanılan bir şablon yardımcı işlevini `pair`, burada bileşen türleri parametre olarak geçirilen veri türlerini temel alır.|
|[Taşıma](../standard-library/utility-functions.md#move)|Bağımsız değişken olarak geçirilen döndürür bir `rvalue` başvuru.|
|[değiştirme](../standard-library/utility-functions.md#swap)|İki öğeleri birbiriyle değiştirir `pair` nesneleri.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|İşlecin sol tarafındaki çift nesnesi işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|İşlecin sol tarafındaki çifti nesnesinin işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.|
|[işleç <](../standard-library/utility-operators.md#op_lt)|İşlecin sol tarafta çift nesnesi olup olmadığını test eder çifti nesnesinin işlecin sağ tarafındaki küçüktür.|
|[İşleci\<=](../standard-library/utility-operators.md#op_gt_eq)|İşlecinin sol tarafta çift nesnesi küçük olup olmadığını sınar veya işlecin sağ tarafındaki çift nesnesi eşittir.|
|[operator >](../standard-library/utility-operators.md#op_gt)|İşlecin sol tarafındaki çifti nesnesinin işlecin sağ tarafındaki çift nesnesi büyük olup olmadığını sınar.|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|İşlecin sol tarafındaki çift nesnesi büyük veya işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[Kimlik](../standard-library/identity-structure.md)||
|[çifti](../standard-library/pair-structure.md)|İki nesne tek bir nesne olarak değerlendir olanağı sağlayan bir tür.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
