---
title: _query_new_handler
ms.date: 11/04/2016
apiname:
- _query_new_handler
apilocation:
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
apitype: DLLExport
f1_keywords:
- _query_new_handler
- query_new_handler
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
ms.openlocfilehash: febefbe46d95b7e5c8de026806a20d7eff74e7cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516005"
---
# <a name="querynewhandler"></a>_query_new_handler

Geçerli yeni işleyici rutinini adresini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

Tarafından belirlenen geçerli yeni işleyici rutinini adresini döndürür **_set_new_handler**.

## <a name="remarks"></a>Açıklamalar

C++ **_query_new_handler** işlev kümesi tarafından C++ geçerli özel durum işleme işlevin adresini döndürür [_set_new_handler](set-new-handler.md) işlevi. **_set_new_handler** denetimi elde etmek için bir özel durum işleme işlevi belirtmek için kullanılan **yeni** işleci başarısız bellek ayrılamadı. Daha fazla bilgi için bkz [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) C++ dil başvurusu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_handler**|\<New.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
