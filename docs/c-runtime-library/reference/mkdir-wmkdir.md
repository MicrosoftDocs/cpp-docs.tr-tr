---
title: _mkdir, _wmkdir
ms.date: 11/04/2016
apiname:
- _wmkdir
- _mkdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 0d89e1f0930cf9131156a4691069f1f17c15c124
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496625"
---
# <a name="mkdir-wmkdir"></a>_mkdir, _wmkdir

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
Yeni bir dizin yolu.

## <a name="return-value"></a>Dönüş Değeri

Yeni dizin oluşturduysanız bu işlevlerin her biri 0 değerini döndürür. Bir hata, işlev -1 döndürür ve kümeleri **errno** gibi.

**EEXIST** çünkü dizin oluşturulmadı *DizinAdı* bir var olan dosya, dizin veya cihaz adıdır.

**ENOENT** yolu bulunamadı.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Mkdir** işlevi yeni bir dizin belirtilen oluşturur *DizinAdı.* **_mkdir** yalnızca son bileşeni, çağrı başına yalnızca bir yeni dizine oluşturabilirsiniz *DizinAdı* yeni bir dizin adı. **_mkdir** yolu sınırlayıcı anlamına gelmez. Windows NT, her iki eğik çizgi ( \\) ve eğik çizgi (/) çalışma zamanı yordamları karakter dizesinin geçerli yolu sınırlayıcı.

**_wmkdir** geniş karakterli sürümüdür **_mkdir**; *DizinAdı* bağımsız değişkeni **_wmkdir** geniş karakterli bir dizedir. **_wmkdir** ve **_mkdir** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmkdir**|**_mkdir**|**_mkdir**|**_wmkdir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mkdir**|\<Direct.h >|
|**_wmkdir**|\<Direct.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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
