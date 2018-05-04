---
title: _query_new_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 340574a57bf1e6309ac9a5e1aa59b7e28632ae59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="querynewhandler"></a>_query_new_handler

Geçerli yeni işleyici yordamı adresini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>Dönüş Değeri

Tarafından belirlenen geçerli yeni işleyici yordamının adresi döndürür **_set_new_handler**.

## <a name="remarks"></a>Açıklamalar

C++ **_query_new_handler** işlevi döndürür kümesi tarafından C++ geçerli özel durum işleme işlevin adresini [_set_new_handler](set-new-handler.md) işlevi. **_set_new_handler** , Denetim kazanmak için bir özel durum işleme işlevi belirtmek için kullanılan **yeni** işleci başarısız bellek ayıramadı. Açıklamalara daha fazla bilgi için bkz: [yeni ve delete işleçleri](../../cpp/new-and-delete-operators.md) C++ dil başvurusu.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_query_new_handler**|\<New.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
