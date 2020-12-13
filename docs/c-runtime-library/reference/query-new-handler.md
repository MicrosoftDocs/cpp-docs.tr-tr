---
description: 'Hakkında daha fazla bilgi edinin: _query_new_handler'
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
ms.openlocfilehash: 8479ad1ffc6ec03d3cff82df645255fc69b16257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137156"
---
# <a name="_query_new_handler"></a>_query_new_handler

Geçerli yeni işleyici yordamının adresini döndürür.

## <a name="syntax"></a>Syntax

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

**_Set_new_handler** tarafından ayarlanan geçerli yeni işleyici yordamının adresini döndürür.

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
