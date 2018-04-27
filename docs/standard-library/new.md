---
title: '&lt;Yeni&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <new>
dev_langs:
- C++
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17a72100dbfb51fae9085e3900cd180bde0a31be
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltnewgt"></a>&lt;new&gt;

Birkaç türler ve İşlevler, Denetim ayırma ve depolama program denetimindeki boşaltma tanımlar. Ayrıca, Depolama Yönetimi hatalarını raporlama bileşenleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <new>

```

## <a name="remarks"></a>Açıklamalar

Bu başlığında bildirilen işlevler bazıları değiştirilebilir. Uygulama, davranış bu belgede açıklanan varsayılan sürüm, sağlar. Ancak, bir program işlevi varsayılan sürümü bağlantı aynı anda değiştirmek için aynı imzayla tanımlayabilirsiniz. Değiştirme sürümü, bu belgede açıklanan gereksinimleri karşılaması gerekir.

### <a name="objects"></a>Nesneler

|||
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|Bir bağımsız değişken olarak kullanılacak bir nesneyi sağlar `nothrow` sürümleri **yeni** ve **silmek**.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Yeni bir işleyici olarak kullanım için uygun bir işlev işaret türü.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Yükler yeni adlı bir kullanıcı işlevi bellek ayıramadı, girişimi başarısız olur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[delete işleci](../standard-library/new-operators.md#op_delete)|Tek tek nesnelerin için depolama alanı ayırması için bir silme ifadesi tarafından çağrılan işlev.|
|[delete işleci&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|Nesne dizisi için depolama alanı ayırması için bir silme ifadesi tarafından çağrılan işlev.|
|[new işleci](../standard-library/new-operators.md#op_new)|Ayrı ayrı nesneleri için depolama alanı ayırmak için yeni bir ifade tarafından çağrılan işlev.|
|[new işleci&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Nesne dizisi için depolama alanı ayırmak için yeni bir ifade tarafından çağrılan işlev.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[bad_alloc Sınıfı](../standard-library/bad-alloc-class.md)|Ayırma isteği başarılı olmadı belirtmek için bir özel durum sınıfı tanımlar.|
|[nothrow_t sınıfı](../standard-library/nothrow-t-structure.md)|Sınıf işleci işlevi parametre olarak yeni işlev yerine bir ayırma hatası rapor için bir özel durum null işaretçi döndürmesi gerektiğini belirtmek için kullanılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
