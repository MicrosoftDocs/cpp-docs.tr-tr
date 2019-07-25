---
title: '&lt;Utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: eaae94bcffcda6e113001dd7070bcc80e7c14d09
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458073"
---
# <a name="ltutilitygt"></a>&lt;Utility&gt;

İki C++ nesne bir tane gibi ele alınamadığında yararlı olan nesne çiftlerini oluşturma ve yönetmeye yardımcı olan standart kitaplık türlerini, işlevleri ve işleçleri tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yardımcı program >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Çiftler C++ standart kitaplıkta yaygın olarak kullanılır. Bunlar hem bağımsız değişkenler hem de çeşitli işlevler için dönüş değerleri ve [eşleme sınıfı](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md)gibi kapsayıcılar için öğe türleri olarak istenir. Yardımcı program > üst bilgisi, anahtar/ \<değer çifti türü öğelerinin yönetilmesine yardımcı olmak için harita > tarafından otomatik olarak eklenir. \<

> [!NOTE]
> Yardımcı program > üst bilgisi, ifadesini `#include <initializer_list>`kullanır. \< Ayrıca, > tanımlama `class tuple` alanında \<tanımlanan olarak da ifade eder.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|İlkel sayısal dönüştürme için kayan nokta biçimi.|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Bir `pair` öğenin türünü sarmalayan sınıf.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Öğe sayısını sarmalayan `pair` sınıf.|

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
|[declval](../standard-library/utility-functions.md#declval)|Toplu ifade değerlendirmesi.|
|[exchange](../standard-library/utility-functions.md#exchange)|Nesnesine yeni bir değer atar ve eski değerini döndürür.|
|[tirler](../standard-library/utility-functions.md#forward)|Bağımsız değişkenin başvuru türünü (ya `lvalue` da `rvalue`), kusursuz iletme tarafından gizlenmeden korur.|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[get](../standard-library/utility-functions.md#get)|`pair` Nesnesinden bir öğe alan bir işlev.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Türü `pair`nesneleri oluşturmak için kullanılan bir şablon Yardımcısı işlevi, bileşen türlerinin parametre olarak geçirilen veri türlerini temel alır.|
|[geçiş](../standard-library/utility-functions.md#move)|Geçirilen bağımsız değişkeni bir `rvalue` başvuru olarak döndürür.|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[Kur](../standard-library/utility-functions.md#swap)|İki `pair` nesnenin öğelerini değiş tokuş eder.|
|[to_chars](../standard-library/utility-functions.md#to_chars)|Değeri bir karakter dizesine dönüştürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneye eşit olup olmadığını sınar.|
|[işlecinde\<](../standard-library/utility-operators.md#op_lt)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden daha az olup olmadığını sınar.|
|[işlecinde\<=](../standard-library/utility-operators.md#op_gt_eq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden küçük veya ona eşit olup olmadığını sınar.|
|[işleç >](../standard-library/utility-operators.md#op_gt)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|İşlecin sol tarafındaki çift nesnenin sağ taraftaki çift nesneden büyük veya ona eşit olup olmadığını sınar.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|İçin `from_chars`kullanılan bir struct.|
|[IDENTITY](../standard-library/identity-structure.md)|Şablon parametresi olarak bir tür tanımı sağlayan bir struct.|
|[in_place_t](../standard-library/in-place-t-struct.md)|Ayrıca yapılar `in_place_type_t` ve `in_place_index_t`içerir.|
|[integer_sequence](../standard-library/integer-sequence-class.md)|Bir tamsayı dizisini temsil eder.|
|[çifti](../standard-library/pair-structure.md)|İki nesneyi tek bir nesne olarak işleme yeteneği sağlayan bir tür.|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|Ayrı oluşturucuyu ve işlev aşırı yüklemesini tutmak için kullanılan bir tür.|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|İçin `to_chars`kullanılan bir struct.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
