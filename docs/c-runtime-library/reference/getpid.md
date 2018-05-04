---
title: _getpid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getpid
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getpid
dev_langs:
- C++
helpviewer_keywords:
- getpid function
- _getpid function
- process identification numbers
ms.assetid: d3e13bae-9a0c-4f33-86d3-ec9df9519285
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f93f6c1c70618b300e8bc05b8e3a15104de6fa6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="getpid"></a>_getpid

İşlem kimliği alır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _getpid( void );
```

## <a name="return-value"></a>Dönüş Değeri

Sistemden elde edilen işlem kimliği döndürür. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

**_Getpid** işlevi sistemden işlem kimliği alır. İşlem kimliği, arama işlemi benzersiz olarak tanımlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getpid**|\<Process.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getpid.c
// This program uses _getpid to obtain
// the process ID and then prints the ID.

#include <stdio.h>
#include <process.h>

int main( void )
{
   // If run from command line, shows different ID for
   // command line than for operating system shell.

   printf( "Process id: %d\n", _getpid() );
}
```

```Output
Process id: 3584
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_mktemp, _wmktemp](mktemp-wmktemp.md)<br/>
