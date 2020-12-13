---
description: 'Hakkında daha fazla bilgi edinin: _get_terminate'
title: _get_terminate
ms.date: 4/2/2020
api_name:
- _get_terminate
- _o__get_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_terminate
- _get_terminate
- __get_terminate
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
ms.openlocfilehash: 958ecb51620497c459b0505431036d5e9d546862
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338975"
---
# <a name="_get_terminate"></a>_get_terminate

**Terminate** tarafından çağrılacak sonlandırma yordamını döndürür.

## <a name="syntax"></a>Syntax

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>Dönüş Değeri

[Set_terminate](set-terminate-crt.md)tarafından kaydedilen işleve bir işaretçi döndürür. Hiçbir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer **null** olabilir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)<br/>
[durdur](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
