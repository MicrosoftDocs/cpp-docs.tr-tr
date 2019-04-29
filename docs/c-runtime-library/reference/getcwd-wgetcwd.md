---
title: _getcwd, _wgetcwd
ms.date: 11/04/2016
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
ms.openlocfilehash: 4c533f0e716cb9a13c152b9be3c46f60291118d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331798"
---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd

Geçerli çalışma dizini alır.

## <a name="syntax"></a>Sözdizimi

```C
char *_getcwd(
   char *buffer,
   int maxlen
);
wchar_t *_wgetcwd(
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Karakter cinsinden yolun en fazla uzunluk: **char** için **_getcwd** ve **wchar_t** için **_wgetcwd**.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür *arabellek*. A **NULL** dönüş değeri bir hata gösterir ve **errno** ya da ayarlanmış **ENOMEM**, ayırmak için yeterli bellek olduğunu belirten *maxlen* bayt (zaman bir **NULL** bağımsız değişken olarak verilir *arabellek*), veya **ERANGE**, yolun daha uzun olduğunu belirten *maxlen*  karakter. Varsa *maxlen* küçük veya ona eşit sıfır olarak açıklandığı gibi bu işlev, geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getcwd** işlevi varsayılan sürücüsü için geçerli çalışma dizininin tam yolunu alır ve depolar *arabellek*. Tamsayı bağımsız değişkeni *maxlen* yolu için uzunluk üst sınırını belirtir. (Sondaki boş karakter dahil) yol uzunluğunu aşıyor, bir hata meydana gelir *maxlen*. *Arabellek* bağımsız değişkeni olabilir **NULL**; arabellek boyutu en az bir *maxlen* (daha fazla yalnızca gerekli olduğunda) otomatik olarak tahsis edildiği, kullanarak **malloc**depolamak için. Bu arabellek daha sonra çağrılarak serbest bırakılabileceğini **ücretsiz** ve geçirerek **_getcwd** (ayrılan arabelleğin işaretçisini) değeri döndürür.

**_getcwd** geçerli çalışma dizini yolu temsil eden bir dize döndürür. Geçerli çalışma dizini kök ise dize ters eğik çizgi ile sona erer ( **\\** ). Geçerli çalışma dizini kök dışında bir dizin ise, dize olmayan bir ters eğik çizgi ile dizin adı ile sona erer.

**_wgetcwd** geniş karakterli sürümüdür **_getcwd**; *arabellek* bağımsız değişkeni ve dönüş değerini **_wgetcwd** geniş karakterli dizelerdir. **_wgetcwd** ve **_getcwd** aynı şekilde davranır.

Zaman **_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_getcwd** ve **_wgetcwd** çağrılarıyla değiştirilir **_ getcwd_dbg** ve **_wgetcwd_dbg** bellek ayırmaları hata ayıklama için izin vermek için. Daha fazla bilgi için [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd**|\<Direct.h >|
|**_wgetcwd**|\<Direct.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
