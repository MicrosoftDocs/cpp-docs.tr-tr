---
title: _onexit, _onexit_m
ms.date: 11/04/2016
apiname:
- _onexit
- _onexit_m
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
apitype: DLLExport
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
ms.openlocfilehash: c190f777032904802f771bab9fc323ba305ff32e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156051"
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m

Çıkış zaman çağrılacak bir yordam kaydeder.

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

*İşlevi*<br/>
Çıkışta çağrılmak için bir işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**_onexit** başarılı olursa işlevine bir işaretçi döndürür veya **NULL** işlev işaretçisi depolamak için boşluk varsa.

## <a name="remarks"></a>Açıklamalar

**_Onexit** işlevi, bir işlevin adresini geçirilir (*işlevi*) programın normal şekilde sonlandırıldığında çağrılabilir. Art arda çağrılar **_onexit** LIFO (son giren ilk-çıkar) sırayla yürütülen işlevler bir kasa oluşturun. İşleve geçirilen **_onexit** parametreleri alamıyor.

Durumda olduğunda **_onexit** kayıtlı yordamları bir DLL içinde çağrılır **_onexit** bir DLL çalıştırmada kaldırma sonrasında **DllMain** DLL_PROCESS_DETACH ile adlandırılır.

**_onexit** bir Microsoft uzantısıdır. ANSI taşınabilirliğinin için kullanmak [atexit](atexit.md). **_Onexit_m** sürümüdür işlevi için karma mod kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_onexit**|\<stdlib.h >|

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
