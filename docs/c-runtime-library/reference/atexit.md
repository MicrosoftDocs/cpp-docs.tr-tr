---
title: atexit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- atexit
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
- atexit
dev_langs:
- C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d66954348d5d812fac7eca0b231304267cc26157
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393140"
---
# <a name="atexit"></a>atexit

Belirtilen işlev Çıkışta işler.

## <a name="syntax"></a>Sözdizimi

```C
int atexit(
   void (__cdecl *func )( void )
);
```

### <a name="parameters"></a>Parametreler

*FUNC*<br/>
Çağrılacak işlev.

## <a name="return-value"></a>Dönüş Değeri

**atexit** bir hata oluşursa 0 başarılı olursa ya da sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Atexit** işlevi bir işlevin adresini geçirilen *func* program normal şekilde sonlandırıldığında çağrılabilir. Art arda çağrılar **atexit** son giren ilk çıkar (LIFO) sırayla yürütülen işlevlerin bir kayıt oluşturun. İşlevler geçirilen **atexit** parametreleri alamıyor. **atexit** ve **_onexit** öbek işlevleri kayıt tutmak için kullanın. Bu nedenle, yalnızca yığın bellek tarafından kaydedilebilir işlev sayısı sınırlıdır.

Kodda **atexit** işlevi, ne zaman bellekten zaten herhangi bir DLL bağımlılıkları içermemelidir **atexit** işlevi çağrılır.

ANSI uyumlu bir uygulama oluşturmak için kullanılan ANSI standardına kullanmak **atexit** işlevi (benzer yerine **_onexit** işlevi).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**atexit**|\<stdlib.h >|

## <a name="example"></a>Örnek

Bu program iter dört işlev ne zaman yürütülmeye işlevlerin yığına **atexit** olarak adlandırılır. Program çıktığında bu programlar, son üzerinde ilk olarak yürütülür.

```C
// crt_atexit.c
#include <stdlib.h>
#include <stdio.h>

void fn1( void ), fn2( void ), fn3( void ), fn4( void );

int main( void )
{
   atexit( fn1 );
   atexit( fn2 );
   atexit( fn3 );
   atexit( fn4 );
   printf( "This is executed first.\n" );
}

void fn1()
{
   printf( "next.\n" );
}

void fn2()
{
   printf( "executed " );
}

void fn3()
{
   printf( "is " );
}

void fn4()
{
   printf( "This " );
}
```

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
