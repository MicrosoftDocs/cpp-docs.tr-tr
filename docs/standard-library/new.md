---
title: '&lt;new&gt;'
ms.date: 11/04/2016
f1_keywords:
- <new>
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
ms.openlocfilehash: bc873f278461fcdc6dbb42e7c968c691e3dc7f73
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243546"
---
# <a name="ltnewgt"></a>&lt;new&gt;

Çeşitli türleri ve işlevleri denetleyen ayırma ve program denetiminin altında depolama boşaltma tanımlar. Ayrıca, Depolama Yönetimi hatalarını raporlama bileşenleri tanımlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yeni >

**Namespace:** std

## <a name="remarks"></a>Açıklamalar

Bu üstbilgisinde bildirilen işlevlerin bazıları değiştirilebilir. Uygulama davranışı, bu belgede açıklanan varsayılan sürümü sağlar. Ancak, bir program bağlantı zamanında varsayılan sürümünü değiştirmek için aynı imzaya sahip bir işlev tanımlayabilirsiniz. En yeni sürümü, bu belgede açıklanan gereksinimleri karşılaması gerekir.

## <a name="members"></a>Üyeler

### <a name="objects"></a>Nesneler

|||
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|Bir bağımsız değişken olarak kullanılacak nesne sağlar **nothrow** sürümlerini **yeni** ve **Sil**.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Yeni bir işleyici olarak kullanım için bir işleve işaret eden bir tür.|
|[hardware_constructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||
|[hardware_destructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||

### <a name="functions"></a>İşlevler

|||
|-|-|
|[get_new_handler](../standard-library/new-functions.md#get_new_handler)||
|[launder](../standard-library/new-functions.md#launder)||
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Yükler, yeni çağrılan bir kullanıcı işlevi bellek ayırmak için kendi girişimi başarısız olur.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[delete işleci](../standard-library/new-operators.md#op_delete)|Tek nesne için depolama ayırması için ifadeyi silmenin tarafından çağrılan işlev.|
|[delete işleci&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|Bir nesne dizisi için depolama ayırması için ifadeyi silmenin tarafından çağrılan işlev.|
|[new işleci](../standard-library/new-operators.md#op_new)|Tek tek nesneler için depolama alanı ayırmak için yeni bir ifade tarafından çağrılan işlev.|
|[new işleci&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Bir nesne dizisi için ayrılacak yeni bir ifade tarafından çağrılan işlev.|

### <a name="enums"></a>Numaralandırmalar

|||
|-|-|
|[align_val_t](../standard-library/new-operators.md#op_align_val_t)||

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[bad_alloc Sınıfı](../standard-library/bad-alloc-class.md)|Sınıf bir ayırma isteği başarılı olmadı belirtmek için bir durum tanımlıyor.|
|[bad_array_new_length sınıfı](../standard-library/bad-array-new-length.md)||
|[nothrow_t sınıfı](../standard-library/nothrow-t-structure.md)|Sınıf operatör işlevi parametre olarak yeni işlevi yerine bir ayırma hatası rapor için bir özel durum null bir işaretçi döndürmesi gerektiğini belirtmek için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
