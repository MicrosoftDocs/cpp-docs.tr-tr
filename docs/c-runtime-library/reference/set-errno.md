---
title: _set_errno
ms.date: 11/04/2016
api_name:
- _set_errno
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_errno
- _set_errno
helpviewer_keywords:
- errno global variable
- set_errno function
- _set_errno function
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
ms.openlocfilehash: 09800276886ecf1c2fdd2ffee63ddcb8cc57f61e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948600"
---
# <a name="_set_errno"></a>_set_errno

**Errno** genel değişkeninin değerini ayarlayın.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _set_errno( int error_value );
```

### <a name="parameters"></a>Parametreler

*error_value*<br/>
**Errno**'nun yeni değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

Olası değerler errno. h içinde tanımlanır. Ayrıca bkz. [errno sabitleri](../../c-runtime-library/errno-constants.md).

## <a name="example"></a>Örnek

```C
// crt_set_errno.c
#include <stdio.h>
#include <errno.h>

int main()
{
   _set_errno( EILSEQ );
   perror( "Oops" );
}
```

```Output
Oops: Illegal byte sequence
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_set_errno**|\<Stdlib. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_get_errno](get-errno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
