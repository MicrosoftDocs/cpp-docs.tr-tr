---
title: _getmaxstdio
ms.date: 11/04/2016
apiname:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmaxstdio
- getmaxstdio
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
ms.openlocfilehash: ea8e516b4c0806230376ea52e399c9fa1f9a858a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331733"
---
# <a name="getmaxstdio"></a>_getmaxstdio

Akış g/ç düzeyi izin verilen eşzamanlı olarak açık dosyaların sayısını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _getmaxstdio( void );
```

## <a name="return-value"></a>Dönüş Değeri

İzin şu anda aynı anda açık dosya sayısını temsil eden bir sayı döndürür **stdio** düzeyi.

## <a name="remarks"></a>Açıklamalar

Kullanım [_setmaxstdio](setmaxstdio.md) izin aynı anda açık dosya sayısını yapılandırmak için **stdio** düzeyi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getmaxstdio**|\<stdio.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
