---
description: 'Hakkında daha fazla bilgi edinin: _onexit _onexit_m'
title: _onexit, _onexit_m
ms.date: 11/04/2016
api_name:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
ms.openlocfilehash: 0b79c521b04a4cb1597dda7c7ed2a19ae2dcf905
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151703"
---
# <a name="_onexit-_onexit_m"></a>_onexit, _onexit_m

Çıkış zamanında çağrılması için bir yordam kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>Parametreler

*çalışmayacaktır*<br/>
Çıkışta çağrılacak işleve yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_onexit** , işlev işaretçisinin depolanması için boşluk yoksa, başarılı veya **null** ise işleve bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Onexit** işlevi, program normal olarak sonlandırıldığında çağrılacak bir işlevin (*işlev*) adresini geçti. **_Onexit** için art arda yapılan ÇAĞRıLAR, LIFO (ilk kez geçen) sırada yürütülen işlevlerin bir kaydını oluşturur. **_Onexit** geçirilen işlevler parametre alamaz.

**_ONEXIT** dll içinden çağrıldığında, **_onexit** Ile kaydedilen yordamlar, **DLLMAIN** DLL_PROCESS_DETACH ile çağrıldıktan sonra dll 'nin kaldırılması durumunda çalıştırılır.

**_onexit** bir Microsoft uzantısıdır. ANSI taşınabilirlik için [atexit](atexit.md)' i kullanın. İşlevin **_onexit_m** sürümü karma mod kullanımı içindir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>Çıktı

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>
