---
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
ms.openlocfilehash: 9afcd729f19f11b82e8f24c2b7fcf9ec40990deb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951339"
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

**_Onexit** işlevi, program normal olarak sonlandırıldığında çağrılacak bir işlevin (*işlev*) adresini geçti. **_Onexit** için art arda ÇAĞRıLAR, LIFO (ilk kez geçen) sırada yürütülen işlevlerin bir kaydını oluşturur. **_Onexit** öğesine geçirilen işlevler parametre alamaz.

Bir DLL içinden **_onexit** çağrıldığında, **DllMain 'ın DllMain** sonrasında dll 'nin kaldırılması sırasında **_onexit** ile kaydedilen yordamlar DLL_PROCESS_DETACH ile çağırılır.

**_onexit** bir Microsoft uzantısıdır. ANSI taşınabilirlik için [atexit](atexit.md)' i kullanın. İşlevin **_onexit_d** sürümü karma mod kullanımı içindir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_onexit**|\<Stdlib. h >|

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

### <a name="output"></a>Çıkış

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>
