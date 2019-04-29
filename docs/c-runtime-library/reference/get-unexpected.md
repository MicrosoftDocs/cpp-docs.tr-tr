---
title: _get_unexpected
ms.date: 11/04/2016
apiname:
- _get_unexpected
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
apitype: DLLExport
f1_keywords:
- __get_unexpected
- _get_unexpected
- get_unexpected
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
ms.openlocfilehash: 225158ecab60a5997ebedbad107eb43d82189234
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331903"
---
# <a name="getunexpected"></a>_get_unexpected

Çağrılacak sonlandırma yordamını döndürür **beklenmeyen**.

## <a name="syntax"></a>Sözdizimi

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>Dönüş Değeri

Tarafından kaydedilen işlevine bir işaretçi döndürür [set_unexpected](set-unexpected-crt.md). Hiçbir işlev ayarlarsanız dönüş değeri, varsayılan davranışı geri yüklemek için kullanılabilir; Bu değer olabilir **NULL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_unexpected**|\<EH.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
