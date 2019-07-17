---
title: '&lt;yardımcı programı&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 76b04c3c26f6ec49f1d816feaeec7e21312d79a9
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246274"
---
# <a name="ltutilitygt"></a>&lt;yardımcı programı&gt;

C++ standart kitaplık türleri, İşlevler ve oluşturmak ve iki nesne bir oldukları gibi kabul gerektiğinde yararlı olan nesneleri çiftlerini yönetmek üzere Yardım işleçler tanımlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yardımcı programı >

**Namespace:** std

## <a name="remarks"></a>Açıklamalar

Çiftler, C++ Standart Kitaplığı'nda yaygın olarak kullanılır. Çeşitli işlevleri için dönüş değerleri ve bağımsız olarak hem de olduğu gibi kapsayıcılar için öğe türleri olarak gereklidirler [harita sınıfı](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md). \<Yardımcı programı > tarafından otomatik olarak üst bilgisi dahil \<harita >, anahtar/değer yönetilmesine yardımcı olmak için çifti öğelerini yazın.

> [!NOTE]
> \<Yardımcı programı > üstbilgisi kullanan deyim `#include <initializer_list>`. Ayrıca başvurduğu `class tuple` tanımlandığı gibi \<demet >.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|Basit sayısal dönüştürme için kayan nokta biçimi.|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Bir sınıf türü sarmalayan bir `pair` öğesi.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Saran bir sınıf `pair` öğe sayısı.|

### <a name="objects"></a>Nesneler

|||
|-|-|
|[index_sequence](../standard-library/utility-functions.md#index_sequence)||
|[index_sequence_for](../standard-library/utility-functions.md#index_sequence_for)||
|[make_index_sequence](../standard-library/utility-functions.md#make_index_sequence)||
|[make_integer_sequence](../standard-library/utility-functions.md#make_integer_sequence)||

### <a name="functions"></a>İşlevler

|||
|-|-|
|[as_const](../standard-library/utility-functions.md#asconst)|Türü döndürür.|
|[declval](../standard-library/utility-functions.md#declval)|Kısaca ifade değerlendirmesi.|
|[exchange](../standard-library/utility-functions.md#exchange)|Bir nesneye yeni bir değer atar ve eski değeri döndürür.|
|[İleriye doğru](../standard-library/utility-functions.md#forward)|Başvuru türü korur (ya da `lvalue` veya `rvalue`) tarafından kusursuz iletme engellediği gelen bağımsız değişken.|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[get](../standard-library/utility-functions.md#get)|Bir öğeyi alır bir işlev bir `pair` nesne.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Türündeki nesneler oluşturmak için kullanılan bir şablon yardımcı işlevini `pair`, burada bileşen türleri parametre olarak geçirilen veri türlerini temel alır.|
|[Taşıma](../standard-library/utility-functions.md#move)|Bağımsız değişken olarak geçirilen döndürür bir `rvalue` başvuru.|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[değiştirme](../standard-library/utility-functions.md#swap)|İki öğeleri birbiriyle değiştirir `pair` nesneleri.|
|[to_chars](../standard-library/utility-functions.md#to_chars)|Değer, bir karakter dizisine dönüştürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|İşlecin sol tarafındaki çift nesnesi işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|İşlecin sol tarafındaki çifti nesnesinin işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.|
|[İşleci\<](../standard-library/utility-operators.md#op_lt)|İşlecin sol tarafta çift nesnesi olup olmadığını test eder çifti nesnesinin işlecin sağ tarafındaki küçüktür.|
|[İşleci\<=](../standard-library/utility-operators.md#op_gt_eq)|İşlecinin sol tarafta çift nesnesi küçük olup olmadığını sınar veya işlecin sağ tarafındaki çift nesnesi eşittir.|
|[operator >](../standard-library/utility-operators.md#op_gt)|İşlecin sol tarafındaki çifti nesnesinin işlecin sağ tarafındaki çift nesnesi büyük olup olmadığını sınar.|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|İşlecin sol tarafındaki çift nesnesi büyük veya işlecin sağ tarafındaki çifti nesneye eşit olup olmadığını sınar.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|İçin kullanılan bir yapının `from_chars`.|
|[Kimlik](../standard-library/identity-structure.md)|Şablon parametresi olarak bir tür tanımı sağlayan bir yapı.|
|[in_place_t](../standard-library/in-place-t-struct.md)|Ayrıca yapılar içerir `in_place_type_t` ve `in_place_index_t`.|
|[integer_sequence](../standard-library/integer-sequence-class.md)|Bir tamsayı dizisi temsil eder.|
|[çifti](../standard-library/pair-structure.md)|İki nesne tek bir nesne olarak değerlendir olanağı sağlayan bir tür.|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|Ayrı bir oluşturucu ve işlev aşırı yüklemesi tutmak için kullanılan bir tür.|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|İçin kullanılan bir yapının `to_chars`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
