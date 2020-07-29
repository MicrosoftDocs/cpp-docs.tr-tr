---
title: '&lt;Utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 1beade28ceec0f1552def4bc70c2e95e6b2aa24d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215445"
---
# <a name="ltutilitygt"></a>&lt;Utility&gt;

Her iki nesnenin de olduğu gibi ele alınmaları gerektiğinde yararlı olan nesne çiftlerini oluşturma ve yönetmeye yardımcı olan C++ standart kitaplık türlerini, işlevlerini ve işleçlerini tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<utility>

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Çiftler, C++ standart kitaplığı 'nda yaygın olarak kullanılır. Bunlar hem bağımsız değişkenler hem de çeşitli işlevler için dönüş değerleri ve [eşleme sınıfı](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md)gibi kapsayıcılar için öğe türleri olarak istenir. \<utility>Üst bilgi, \<map> anahtar/değer çifti türü öğelerinin yönetilmesine yardımcı olmak için tarafından otomatik olarak eklenir.

> [!NOTE]
> \<utility>Üst bilgi, ifadesini kullanır `#include <initializer_list>` . Ayrıca `class tuple` , içinde tanımlandığı gibi anlamına gelir \<tuple> .

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Tür|Description|
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|İlkel sayısal dönüştürme için kayan nokta biçimi.|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Bir öğenin türünü sarmalayan sınıf `pair` .|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Öğe sayısını sarmalayan sınıf `pair` .|

### <a name="objects"></a>Nesneler

|Şablon|Açıklama|
|-|-|
|[index_sequence](../standard-library/utility-functions.md#index_sequence)|Burada olduğu yaygın durum için tanımlanan diğer ad şablonu `T``std::size_t`  |
|[index_sequence_for](../standard-library/utility-functions.md#index_sequence_for)|Herhangi bir tür parametre paketini aynı uzunlukta bir dizin dizisine dönüştürecek yardımcı diğer ad şablonu|
|[make_index_sequence](../standard-library/utility-functions.md#make_index_sequence)| Bir türün oluşturulmasını basitleştirmek için yardımcı diğer ad şablonu `std::index_sequence` . |
|[make_integer_sequence](../standard-library/utility-functions.md#make_integer_sequence)|Bir türün oluşturulmasını basitleştirmek için yardımcı diğer ad şablonu `std::integer_sequence` .|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[as_const](../standard-library/utility-functions.md#asconst)|Türü döndürür.|
|[declval](../standard-library/utility-functions.md#declval)|Toplu ifade değerlendirmesi.|
|[değişimi](../standard-library/utility-functions.md#exchange)|Nesnesine yeni bir değer atar ve eski değerini döndürür.|
|[tirler](../standard-library/utility-functions.md#forward)|Bağımsız değişkenin başvuru türünü (ya `lvalue` da `rvalue` ), kusursuz iletme tarafından gizlenmeden korur.|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[Al](../standard-library/utility-functions.md#get)|Nesnesinden bir öğe alan bir işlev `pair` .|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Türü nesneleri oluşturmak için kullanılan bir şablon Yardımcısı işlevi `pair` , bileşen türlerinin parametre olarak geçirilen veri türlerini temel alır.|
|[geçiş](../standard-library/utility-functions.md#move)|Geçirilen bağımsız değişkeni bir başvuru olarak döndürür `rvalue` .|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[Kur](../standard-library/utility-functions.md#swap)|İki nesnenin öğelerini değiş tokuş eder `pair` .|
|[to_chars](../standard-library/utility-functions.md#to_chars)|Değeri bir karakter dizesine dönüştürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](../standard-library/utility-operators.md#op_neq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.|
|[işleç = =](../standard-library/utility-operators.md#op_eq_eq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.|
|[işleç\<](../standard-library/utility-operators.md#op_lt)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden daha az olup olmadığını sınar.|
|[işleç\<=](../standard-library/utility-operators.md#op_gt_eq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç>](../standard-library/utility-operators.md#op_gt)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük olup olmadığını sınar.|
|[işleç>=](../standard-library/utility-operators.md#op_gt_eq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük veya ona eşit olup olmadığını sınar.|

### <a name="structs"></a>Yapılar

|Yapı|Açıklama|
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|İçin kullanılan bir struct `from_chars` .|
|[IDENTITY](../standard-library/identity-structure.md)|Şablon parametresi olarak bir tür tanımı sağlayan bir struct.|
|[in_place_t](../standard-library/in-place-t-struct.md)|Ayrıca yapılar `in_place_type_t` ve içerir `in_place_index_t` .|
|[integer_sequence](../standard-library/integer-sequence-class.md)|Bir tamsayı dizisini temsil eder.|
|[Eşleştir](../standard-library/pair-structure.md)|İki nesneyi tek bir nesne olarak işleme yeteneği sağlayan bir tür.|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|Ayrı oluşturucuyu ve işlev aşırı yüklemesini tutmak için kullanılan bir tür.|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|İçin kullanılan bir struct `to_chars` .|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
