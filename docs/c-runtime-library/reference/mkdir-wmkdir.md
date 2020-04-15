---
title: _mkdir, _wmkdir
ms.date: 4/2/2020
api_name:
- _wmkdir
- _mkdir
- _o__mkdir
- _o__wmkdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mkdir
- tmkdir
- _tmkdir
- wmkdir
- _wmkdir
helpviewer_keywords:
- _wmkdir function
- folders [C++], creating
- wmkdir function
- directories [C++], creating
- mkdir function
- tmkdir function
- _mkdir function
- _tmkdir function
ms.assetid: 7f22d01d-63a5-4712-a6e7-d34878b2d840
ms.openlocfilehash: 56e525dd765ff2594eebcfe9a0aed37670b12e3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338779"
---
# <a name="_mkdir-_wmkdir"></a>_mkdir, _wmkdir

Yeni bir dizin oluşturur.

## <a name="syntax"></a>Sözdizimi

```C

int _mkdir(
   const char *dirname
);
int _wmkdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Parametreler

*dirname*<br/>
Yeni bir dizin için yol.

## <a name="return-value"></a>Dönüş Değeri

Yeni dizin oluşturulduysa, bu işlevlerin her biri 0 değerini döndürür. Bir hatada, işlev -1 döndürür ve **errno'yu** aşağıdaki gibi ayarlar.

**EEXIST** *Dirname* varolan bir dosyanın, dizinin veya aygıtın adı olduğundan dizin oluşturulmadı.

**ENOENT** Yol bulunamadı.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

_mkdir **_mkdir** işlevi belirtilen dirname ile yeni bir dizin *oluşturur.* **_mkdir** çağrı başına yalnızca bir yeni dizin oluşturabilir, böylece *dirnamenin* yalnızca son bileşeni yeni bir dizin adlandırabilir. **_mkdir** yol sınırlayıcıları çevirmez. Windows NT'de, hem \\ters eğik çizgi ( ) hem de ileri eğik çizgi (/ ) çalışma zamanı yordamlarında karakter dizelerinde geçerli yol sınırlayıcılarıdır.

**_wmkdir** **_mkdir**geniş karakterli bir versiyonudur; **_wmkdir** *dirname* bağımsız değişkeni geniş karakterli bir dizedir. **_wmkdir** ve **_mkdir** aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmkdir**|**_mkdir**|**_mkdir**|**_wmkdir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mkdir**|\<direct.h>|
|**_wmkdir**|\<direct.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_makedir.c

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   if( _mkdir( "\\testtmp" ) == 0 )
   {
      printf( "Directory '\\testtmp' was successfully created\n" );
      system( "dir \\testtmp" );
      if( _rmdir( "\\testtmp" ) == 0 )
        printf( "Directory '\\testtmp' was successfully removed\n"  );
      else
         printf( "Problem removing directory '\\testtmp'\n" );
   }
   else
      printf( "Problem creating directory '\\testtmp'\n" );
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Directory '\testtmp' was successfully created
Volume in drive C has no label.
Volume Serial Number is E078-087A

Directory of C:\testtmp

02/12/2002  09:56a      <DIR>          .
02/12/2002  09:56a      <DIR>          ..
               0 File(s)              0 bytes
               2 Dir(s)  15,498,690,560 bytes free
Directory '\testtmp' was successfully removed
```

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
