---
title: _onexit, _onexit_m | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac59e64c1e47d699170af772aeba60a7895dfdc2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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
Çıkışta çağrılacak işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**_onexit** başarılı olursa işlevi için bir işaretçi döndürür veya **NULL** işlev işaretçisi depolamak için hiçbir alan yoksa.

## <a name="remarks"></a>Açıklamalar

**_Onexit** işlevi bir işlevin adresini geçirilen (*işlevi*) programı normal şekilde sonlandırıldığında çağrılabilir. Art arda çağrılar **_onexit** LIFO (son-giren ilk çıkar) sırayla yürütülen işlevlerin bir kayıt oluşturun. İşlevler geçirilen **_onexit** parametreleri alamıyor.

Durumda olduğunda **_onexit** kayıtlı yordamları bir DLL içinde çağrılır **_onexit** DLL çalıştırılmasında sonra yüklemeyi kaldırma **DllMain** DLL_PROCESS_DETACH ile adlandırılır.

**_onexit** bir Microsoft uzantısıdır. ANSI taşınabilirlik için kullanmak [atexit](atexit.md). **_Onexit_m** işlevi sürümüdür için karma mod kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_onexit**|\<stdlib.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
