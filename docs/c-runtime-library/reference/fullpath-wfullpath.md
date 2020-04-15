---
title: _fullpath, _wfullpath
ms.date: 4/2/2020
api_name:
- _fullpath
- _wfullpath
- _o__fullpath
- _o__wfullpath
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
- wfullpath
- fullpath
- _wfullpath
- _fullpath
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
ms.openlocfilehash: 0910cf4f39e00be84e683cd6f3b9afbeb3f2a749
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345492"
---
# <a name="_fullpath-_wfullpath"></a>_fullpath, _wfullpath

Belirtilen göreli yol adı için mutlak veya tam yol adı oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
char *_fullpath(
   char *absPath,
   const char *relPath,
   size_t maxLength
);
wchar_t *_wfullpath(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength
);
```

### <a name="parameters"></a>Parametreler

*absPath*<br/>
Mutlak veya tam yol adını veya **NULL'u**içeren bir arabelleğe işaretçi.

*relPath*<br/>
Göreli yol adı.

*Maxlength*<br/>
Mutlak yol adı arabelleği *(absPath)* maksimum uzunluğu. Bu uzunluk **_fullpath** için bayt, **ancak**_wfullpath için geniş karakterler **(wchar_t)** olarak.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri mutlak yol adı *(absPath)* içeren bir arabellek için bir işaretçi döndürür. Bir hata varsa (örneğin, *relPath'te* geçirilen değer geçerli olmayan veya bulunamayan bir sürücü harfi içeriyorsa veya oluşturulan mutlak yol adının uzunluğu *(absPath)* *maxLength'tan*büyükse ), işlev **NULL'u**döndürür.

## <a name="remarks"></a>Açıklamalar

**_fullpath** işlevi *relPath'teki* göreli yol adını tam nitelikli veya mutlak yoluna genişletir ve bu adı *absPath'te*depolar. *absPath* **NULL**ise, **malloc** yol adını tutmak için yeterli uzunlukta bir arabellek ayırmak için kullanılır. Bu arabelleği serbest etmek arayan kişinin sorumluluğundadır. Göreli bir yol adı, geçerli konumdan başka bir konuma giden bir yol belirtir (geçerli çalışma dizini gibi: "."). Mutlak yol adı, dosya sisteminin kökünden istenen konuma ulaşmak için gereken tüm yolu belirten göreli bir yol adının genişlemesidir. **_makepath** **aksine, _fullpath** "./" veya "...*relPath* /" adlarında.

Örneğin, C çalışma zamanı yordamlarını kullanmak için uygulamanın yordamlar için bildirimleri içeren üstbilgi dosyalarını içermesi gerekir. Her üstbilgi dosyası, dosyanın konumunu göreceli bir şekilde (uygulamanın çalışma dizininden) referanslar içerir:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

dosyanın mutlak yolu (gerçek dosya sistemi konumu) aşağıdakigibi olabilir:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath,** çok bayt karakterli dize bağımsız değişkenlerini uygun şekilde işleyerek, şu anda kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak çalışır. **_wfullpath** **_fullpath**geniş karakterli bir versiyonudur; **_wfullpath** için dize bağımsız değişkenleri geniş karakterli dizeleri vardır. **_wfullpath** ve **_fullpath,** **_wfullpath** çok bayt karakterli dizeleri işlememesi dışında aynı şekilde çalışır.

**_DEBUG** ve **_CRTDBG_MAP_ALLOC** her ikisi de tanımlanırsa, **_fullpath** ve **_wfullpath** çağrıları, bellek ayırmalarının hata ayıklanmasına izin vermek için **_fullpath_dbg** ve **_wfullpath_dbg** çağrılarıyla değiştirilir. Daha fazla bilgi için [_fullpath_dbg _wfullpath_dbg.](fullpath-dbg-wfullpath-dbg.md)

Bu işlev, [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır , *makslen* 0'dan küçük veya eşitse. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL** **için errno** ayarlar ve **NULL**döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

*absPath* arabelleği **NULL**ise, **_fullpath** bir arabellek ayırmak için [malloc](malloc.md) çağırır ve *maxLength* bağımsız değişkeni yoks. Bu arabelleği uygun şekilde [(ücretsiz](free.md)kullanarak) bulmak arayan kişinin sorumluluğundadır. *relPath* bağımsız değişkeni bir disk sürücüsü belirtse, bu sürücünün geçerli dizini yol ile birleştirilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h>|
|**_wfullpath**|\<stdlib.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_fullpath.c
// This program demonstrates how _fullpath
// creates a full path from a partial path.

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <direct.h>

void PrintFullPath( char * partialPath )
{
   char full[_MAX_PATH];
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )
      printf( "Full path is: %s\n", full );
   else
      printf( "Invalid path\n" );
}

int main( void )
{
   PrintFullPath( "test" );
   PrintFullPath( "\\test" );
   PrintFullPath( "..\\test" );
}
```

```Output
Full path is: C:\Documents and Settings\user\My Documents\test
Full path is: C:\test
Full path is: C:\Documents and Settings\user\test
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
