---
title: _getcwd, _wgetcwd
description: C Runtime Kitaplığı işlevleri _getcwd, _wgetcwd geçerli çalışma dizini olsun.
ms.date: 4/2/2020
api_name:
- _wgetcwd
- _getcwd
- _o__getcwd
- _o__wgetcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: bc19a416ebebeb901e8dbb435971e6d5f33e4067
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344442"
---
# <a name="_getcwd-_wgetcwd"></a>_getcwd, _wgetcwd

Geçerli çalışma dizinini alır.

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

*Arabellek*\
Yol için depolama konumu.

*makslen*\
Karakterlerde yolun maksimum uzunluğu: **_getcwd** için **char** ve **_wgetcwd**için **wchar_t.**

## <a name="return-value"></a>Dönüş Değeri

*Arabellek*için bir işaretçi döndürür. **NULL** return value bir hata gösterir ve **errno** **enomem**olarak ayarlanır , *maxlen* bayt ayırmak için yeterli bellek olduğunu belirten **(null** bağımsız *değişkeni arabellek*olarak verildiğinde), veya **ERANGE**, yolun *maxlen* karakterlerden daha uzun olduğunu belirten. *Maxlen* sıfırdan küçük veya eşitse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisini çağırır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_getcwd** işlevi varsayılan sürücü için geçerli çalışma dizininin tam yolunu alır ve *arabellekte*depolar. En üstteki bağımsız *değişken,* yolun en büyük uzunluğunu belirtir. Yolun uzunluğu (sonlandırıcı null karakteri dahil) *maxlen'i*aşarsa bir hata oluşur. Arabellek bağımsız *değişkeni* **NULL**olabilir; en az boyutu *maxlen* bir tampon (daha fazla gerekirse) otomatik olarak tahsis edilir, **malloc**kullanarak , yol saklamak için. Bu arabellek daha sonra **özgür** çağrılarak ve **_getcwd** geri dönüş değeri (ayrılan arabellek için bir işaretçi) geçirerek serbest bırakılabilir.

**_getcwd** geçerli çalışma dizininin yolunu temsil eden bir dize döndürür. Geçerli çalışma dizini kök ise, dize bir ters`\`eğik çizgi ile sona erer ( . Geçerli çalışma dizini kökten başka bir dizinse, dize bir ters eğik çizgiyle değil, dizin adı ile sona erer.

**_wgetcwd** **_getcwd**geniş karakterli bir versiyonudur; *arabellek* bağımsız değişkeni ve **_wgetcwd** döndürme değeri geniş karakterli dizeleri vardır. **_wgetcwd** ve **_getcwd** aynı şekilde davranan.

**_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlandığında, **_getcwd** ve **_wgetcwd** çağrıları, bellek ayırmalarının hata ayıklanmasına izin vermek için **_getcwd_dbg** ve **_wgetcwd_dbg** çağrılarıyla değiştirilir. Daha fazla bilgi için [_getcwd_dbg, _wgetcwd_dbg.](getcwd-dbg-wgetcwd-dbg.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_getcwd.c
// Compile with: cl /W4 crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h> // _getcwd
#include <stdlib.h> // free, perror
#include <stdio.h>  // printf
#include <string.h> // strlen

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if ( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %zu\n", buffer, strlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)\
[_chdir, _wchdir](chdir-wchdir.md)\
[_mkdir, _wmkdir](mkdir-wmkdir.md)\
[_rmdir, _wrmdir](rmdir-wrmdir.md)
