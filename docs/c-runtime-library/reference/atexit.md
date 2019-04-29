---
title: atexit
ms.date: 11/04/2016
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
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
ms.openlocfilehash: 48f0fbfa1f3350f73899fcdbb3bf7922f1c6174d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341593"
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

**atexit** bir hata oluşursa, 0 başarılı olursa ya da sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Atexit** işlevi, bir işlevin adresini geçirilir *func* programın normal şekilde sonlandırıldığında çağrılabilir. Art arda çağrılar **atexit** son giren ilk çıkar (LIFO) sırayla yürütülen işlevler bir kasa oluşturun. İşleve geçirilen **atexit** parametreleri alamıyor. **atexit** ve **_onexit** yığın işlevlerin kayıt tutmak için kullanın. Bu nedenle, kaydedilebilir işlev sayısı yalnızca Yığın bellekle sınırlıdır.

Kodda **atexit** işlevi zaman bellekten zaten, herhangi bir DLL bağımlılıkları içermemelidir **atexit** işlevi çağrılır.

ANSI uyumlu bir uygulama oluşturmak için ANSI standardı kullanın **atexit** işlevi (benzer yerine **_onexit** işlevi).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**atexit**|\<stdlib.h >|

## <a name="example"></a>Örnek

Bu işlevler, yürütülecek yığına program bildirim dört işlev **atexit** çağrılır. Program çıkış yaptığı andaki bu programlar hakkında son giren ilk olarak yürütülür.

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
