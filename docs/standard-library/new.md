---
title: '&lt;Yeni&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <new>
dev_langs:
- C++
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03d4019f86f99c73ccb25c5cf570637dbf0d7753
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966518"
---
# <a name="ltnewgt"></a>&lt;new&gt;

Çeşitli türleri ve işlevleri denetleyen ayırma ve program denetiminin altında depolama boşaltma tanımlar. Ayrıca, Depolama Yönetimi hatalarını raporlama bileşenleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <new>

```

## <a name="remarks"></a>Açıklamalar

Bu üstbilgisinde bildirilen işlevlerin bazıları değiştirilebilir. Uygulama davranışı, bu belgede açıklanan varsayılan sürümü sağlar. Ancak, bir program bağlantı zamanında varsayılan sürümünü değiştirmek için aynı imzaya sahip bir işlev tanımlayabilirsiniz. En yeni sürümü, bu belgede açıklanan gereksinimleri karşılaması gerekir.

### <a name="objects"></a>Nesneler

|||
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|Bir bağımsız değişken olarak kullanılacak nesne sağlar **nothrow** sürümlerini **yeni** ve **Sil**.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Yeni bir işleyici olarak kullanım için bir işleve işaret eden bir tür.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Yükler, yeni çağrılan bir kullanıcı işlevi bellek ayırmak için kendi girişimi başarısız olur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[delete işleci](../standard-library/new-operators.md#op_delete)|Tek nesne için depolama ayırması için ifadeyi silmenin tarafından çağrılan işlev.|
|[delete işleci&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|Bir nesne dizisi için depolama ayırması için ifadeyi silmenin tarafından çağrılan işlev.|
|[new işleci](../standard-library/new-operators.md#op_new)|Tek tek nesneler için depolama alanı ayırmak için yeni bir ifade tarafından çağrılan işlev.|
|[new işleci&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Bir nesne dizisi için ayrılacak yeni bir ifade tarafından çağrılan işlev.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[bad_alloc Sınıfı](../standard-library/bad-alloc-class.md)|Sınıf bir ayırma isteği başarılı olmadı belirtmek için bir durum tanımlıyor.|
|[nothrow_t sınıfı](../standard-library/nothrow-t-structure.md)|Sınıf operatör işlevi parametre olarak yeni işlevi yerine bir ayırma hatası rapor için bir özel durum null bir işaretçi döndürmesi gerektiğini belirtmek için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
