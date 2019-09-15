---
title: _mkdir, _wmkdir
ms.date: 11/04/2016
api_name:
- _wmkdir
- _mkdir
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
ms.openlocfilehash: 0d2fd45b566909a61a04a5cabb34c74b9b253430
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951726"
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

*DizinAdı*<br/>
Yeni bir dizin için yol.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, yeni dizin oluşturulduysa 0 değerini döndürür. Bir hatada, işlev-1 döndürür ve **errno** değerini aşağıdaki şekilde ayarlar.

**Eexist** *Dizinname* mevcut bir dosyanın, dizinin veya cihazın adı olduğundan dizin oluşturulamadı.

**ENOENT** Yol bulunamadı.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Mkdir** işlevi belirtilen *dirname* ile yeni bir dizin oluşturur. **_mkdir** her çağrı için yalnızca bir yeni dizin oluşturabilir, bu nedenle yalnızca *DizinAdı* 'in son bileşeni yeni bir dizin adını verebilir. **_mkdir** yol sınırlayıcılarını çevirmez. Windows NT 'de, ters eğik çizgi ( \\) ve eğik çizgi (/), çalışma zamanı yordamlarında karakter dizelerinde geçerli yol sınırlayıcılardır.

**_wmkdir** , **_mkdir**'in geniş karakterli bir sürümüdür. **_wmkdir** için *DizinAdı* bağımsız değişkeni geniş karakterli bir dizedir. **_wmkdir** ve **_mkdir** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmkdir**|**_mkdir**|**_mkdir**|**_wmkdir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mkdir**|\<Direct. h >|
|**_wmkdir**|\<Direct. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
