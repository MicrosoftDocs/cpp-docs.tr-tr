---
title: _getcwd, _wgetcwd
description: C çalışma zamanı kitaplığı işlevleri _getcwd, _wgetcwd geçerli çalışma dizinini al.
ms.date: 09/24/2019
api_name:
- _wgetcwd
- _getcwd
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
ms.openlocfilehash: 27cfdc1eb59c2de788bbe5963a6fccffcb62cba0
ms.sourcegitcommit: 7750e4c291d56221c8893120c56a1fe6c9af60d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274628"
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

*arabelleğin*\
Yol için depolama konumu.

*maxlen*\
Saniyedeki yolun uzunluk üst sınırı: **_wgetcwd**için Char, **_getcwd** ve **wchar_t** için **karakter** .

## <a name="return-value"></a>Dönüş Değeri

*Arabelleğe*yönelik bir işaretçi döndürür. **Null** dönüş değeri bir hatayı gösterir ve **errno** , *maxlen* bayt ayırmak içinyeterli bellek olduğunu ( **null** bir bağımsız değişken *buffer*olarak verildiğinde) veya ERANGE olarak ayarlandığını belirten, yolun *maxlen* karakterden daha uzun olduğunu gösterir. *Maxlen* değeri sıfıra eşit veya daha küçükse, bu Işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getcwd** işlevi, varsayılan sürücü için geçerli çalışma dizininin tam yolunu alır ve *arabelleğe*kaydeder. *Maxlen* tamsayı bağımsız değişkeni yolun uzunluk üst sınırını belirtir. Yolun uzunluğu (Sonlandırıcı null karakteri dahil) *maxlen*değerini aşarsa bir hata oluşur. *Buffer* bağımsız değişkeni **null**olabilir; yolu depolamak için, **malloc**kullanılarak en az boyut *maxlen* (yalnızca daha fazla) için bir arabellek otomatik olarak ayrılır. Bu arabellek daha sonra **serbest** çağırarak ve **_getcwd** dönüş değeri (ayrılan arabelleğe bir işaretçi) geçirerek serbest bırakılabilirler.

**_getcwd** , geçerli çalışma dizininin yolunu temsil eden bir dize döndürür. Geçerli çalışma dizini kökeyse, dize bir ters eğik çizgiyle (`\`) biter. Geçerli çalışma dizini kök dışında bir dizin ise, dize bir ters eğik çizgiyle değil dizin adıyla biter.

**_wgetcwd** , **_getcwd**; öğesinin geniş karakterli bir sürümüdür **_wgetcwd** 'in *buffer* bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. **_wgetcwd** ve **_getcwd** aynı şekilde davranır.

**_Debug** ve **_Crtdbg_map_ayırma** tanımlandığında, **_getcwd** ve **_wgetcwd** çağrıları, bellek ayırmalarının hata ayıklamasına izin vermek için **_getcwd_dbg** ve **_wgetcwd_dbg** çağrılarıyla değiştirilmiştir. Daha fazla bilgi için bkz. [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getcwd**|\<Direct. h >|
|**_wgetcwd**|\<Direct. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dizin denetimi](../../c-runtime-library/directory-control.md)\
[_chdir, _wchdir](chdir-wchdir.md)\
[_mkdir, _wmkdir](mkdir-wmkdir.md)\
[_rmdir, _wrmdir](rmdir-wrmdir.md)
