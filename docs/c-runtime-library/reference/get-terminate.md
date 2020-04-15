---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: fff90037851b23f3525f514aba0f6f913f9dd776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344930"
---
# <a name="_get_terminate"></a>_get_terminate

Sonlandırma yordamını **sonlandırma**tarafından çağrılacak şekilde verir.

## <a name="syntax"></a>Sözdizimi

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>Dönüş Değeri

[set_terminate](set-terminate-crt.md)tarafından kayıtlı işleve bir işaretçi döndürür. İşlev ayarlanmadıysa, iade değeri varsayılan davranışı geri yüklemek için kullanılabilir; bu değer **NULL**olabilir.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[Iptal](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Sonlandır](terminate-crt.md)<br/>
[Beklen -medik](unexpected-crt.md)<br/>
