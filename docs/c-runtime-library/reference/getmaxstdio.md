---
description: 'Hakkında daha fazla bilgi edinin: _getmaxstdio'
title: _getmaxstdio
ms.date: 11/04/2016
api_name:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmaxstdio
- getmaxstdio
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
ms.openlocfilehash: 78c427ef9e5152708870d7ff48d0a123b7ee5213
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296556"
---
# <a name="_getmaxstdio"></a>_getmaxstdio

Akış g/ç düzeyinde izin verilen aynı anda açık dosya sayısını döndürür.

## <a name="syntax"></a>Syntax

```C
int _getmaxstdio( void );
```

## <a name="return-value"></a>Dönüş Değeri

**Stdio** düzeyinde şu anda izin verilen aynı anda açık dosya sayısını temsil eden bir sayı döndürür.

## <a name="remarks"></a>Açıklamalar

**Stdio** düzeyinde izin verilen aynı anda açık dosya sayısını yapılandırmak için [_setmaxstdio](setmaxstdio.md) kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getmaxstdio**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_setmaxstdio.c
// The program retrieves the maximum number
// of open files and prints the results
// to the console.

#include <stdio.h>

int main()
{
   printf( "%d\n", _getmaxstdio());

   _setmaxstdio(2048);

   printf( "%d\n", _getmaxstdio());
}
```

```Output
512
2048
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
