---
title: _query_new_handler
ms.date: 11/04/2016
api_name:
- _query_new_handler
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _query_new_handler
- query_new_handler
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
ms.openlocfilehash: 9c87a63a9ed94eb1473230aedb5e9c17fcc6410b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216849"
---
# <a name="_query_new_handler"></a>_query_new_handler

Geçerli yeni işleyici yordamının adresini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

**_Set_new_handler**tarafından ayarlanan geçerli yeni işleyici yordamının adresini döndürür.

## <a name="remarks"></a>Açıklamalar

C++ **_query_new_handler** Işlevi, c++ [_set_new_handler](set-new-handler.md) işlevi tarafından ayarlanan geçerli özel durum işleme işlevinin adresini döndürür. **_set_new_handler** , **`new`** işlecin bellek ayıramadığında denetim kazanmak için bir özel durum işleme işlevi belirtmek için kullanılır. Daha fazla bilgi için bkz. C++ dil başvurusunda [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) tartışması.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_handler**|\<new.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[Süz](free.md)<br/>
