---
title: _set_doserrno
ms.date: 4/2/2020
api_name:
- _set_doserrno
- _o__set_doserrno
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
- _set_doserrno
- set_doserrno
helpviewer_keywords:
- _set_doserrno function
- doserrno global variable
- set_doserrno function
- _doserrno global variable
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
ms.openlocfilehash: 9de5ff8ccc4673468628275c3c3366681edc3776
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913062"
---
# <a name="_set_doserrno"></a>_set_doserrno

[_Doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) genel değişkeninin değerini ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _set_doserrno( int error_value );
```

### <a name="parameters"></a>Parametreler

*error_value*<br/>
**_Doserrno**yeni değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

Olası değerler errno. h içinde tanımlanır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_set_doserrno**|\<Stdlib. h>|\<errno. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_doserrno](get-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
