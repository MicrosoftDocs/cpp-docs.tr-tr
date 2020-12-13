---
description: 'Hakkında daha fazla bilgi edinin: _get_unexpected'
title: _get_unexpected
ms.date: 11/04/2016
api_name:
- _get_unexpected
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __get_unexpected
- _get_unexpected
- get_unexpected
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
ms.openlocfilehash: 9c8f21815aa465e1325ef0519ba21abb1e506db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338937"
---
# <a name="_get_unexpected"></a>_get_unexpected

**Beklenmeyen** tarafından çağrılacak sonlandırma yordamını döndürür.

## <a name="syntax"></a>Syntax

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>Dönüş Değeri

[Set_unexpected](set-unexpected-crt.md)tarafından kaydedilen işleve bir işaretçi döndürür. Hiçbir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer **null** olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_unexpected**|\<eh.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)<br/>
[durdur](abort.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
