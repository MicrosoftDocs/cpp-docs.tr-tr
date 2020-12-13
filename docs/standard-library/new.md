---
description: 'Daha fazla bilgi edinin: &lt; Yeni&gt;'
title: '&lt;new&gt;'
ms.date: 11/04/2016
f1_keywords:
- <new>
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
ms.openlocfilehash: c99c036a7b4065e207bfe9ad71eb86e6d5f01d0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338145"
---
# <a name="ltnewgt"></a>&lt;new&gt;

Program denetimi altında depolama alanını ayırmayı ve boşaltmayı denetleyen çeşitli türleri ve işlevleri tanımlar. Ayrıca, depolama yönetimi hatalarını raporlamak için bileşenleri tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<new>

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Bu üst bilgide belirtilen işlevlerden bazıları değiştirilebilir. Uygulama, davranışı bu belgede açıklanan varsayılan sürümü sağlar. Ancak bir program, bağlantı zamanında varsayılan sürümü değiştirmek için aynı imzaya sahip bir işlev tanımlayabilir. Değiştirme sürümünün bu belgede açıklanan gereksinimleri karşılaması gerekir.

## <a name="members"></a>Üyeler

### <a name="objects"></a>Nesneler

|Ad|Açıklama|
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|Ve sürümleri için bağımsız değişken olarak kullanılacak bir nesne sağlar **`nothrow`** **`new`** **`delete`** .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Yeni işleyici olarak kullanım için uygun bir işleve işaret eden bir tür.|
|[hardware_constructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||
|[hardware_destructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[get_new_handler](../standard-library/new-functions.md#get_new_handler)||
|[eksik](../standard-library/new-functions.md#launder)||
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Yeni bir bellek ayırma girişiminde başarısız olduğunda çağrılan bir Kullanıcı işlevi yüklenir.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[delete işleci](../standard-library/new-operators.md#op_delete)|Nesnelerin ayrı olarak depolanmasını serbest bırakmak için bir Delete ifadesi tarafından çağrılan işlev.|
|[Delete&#91;&#93;işleci ](../standard-library/new-operators.md#op_delete_arr)|Bir nesne dizisi için depolamayı serbest bırakmak için bir Delete ifadesi tarafından çağrılan işlev.|
|[New işleci](../standard-library/new-operators.md#op_new)|Ayrı nesneler için depolama alanı ayırmak üzere yeni bir ifade tarafından çağrılan işlev.|
|[New işleci&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Bir nesne dizisi için depolama alanı ayırmak üzere yeni bir ifade tarafından çağrılan işlev.|

### <a name="enums"></a>Numaralandırmalar

|Ad|Açıklama|
|-|-|
|[align_val_t](../standard-library/new-operators.md#op_align_val_t)||

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[bad_alloc sınıfı](../standard-library/bad-alloc-class.md)|Sınıfı, bir ayırma isteğinin başarılı olmadığını göstermek için oluşturulan bir özel durum tanımlar.|
|[bad_array_new_length sınıfı](../standard-library/bad-array-new-length.md)||
|[nothrow_t sınıfı](../standard-library/nothrow-t-structure.md)|Sınıfı, işlevin bir özel durum oluşturmak yerine bir ayırma hatası bildirmek üzere null bir işaretçi döndürmesi gerektiğini göstermek için New işlecine bir Function parametresi olarak kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
