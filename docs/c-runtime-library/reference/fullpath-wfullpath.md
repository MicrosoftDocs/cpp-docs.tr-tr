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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: f7ef9e8416e73a403abfb30f637afeb4a68e8592
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909946"
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
Mutlak veya tam yol adı veya **null**içeren bir arabelleğin işaretçisi.

*relPath*<br/>
Göreli yol adı.

*'In*<br/>
Mutlak yol adı arabelleğinin (*absPath*) uzunluk üst sınırı. Bu uzunluk, **_fullpath** için bayt cinsinden, **_wfullpath**için geniş karakterler (**wchar_t**) cinsinden olur.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, mutlak yol adını (*absPath*) içeren bir arabelleğe yönelik bir işaretçi döndürür. Bir hata varsa (örneğin, *RelPath* içinde geçirilen değer geçerli olmayan veya bulunamayan bir sürücü harfi içeriyorsa veya oluşturulan mutlak yol adının (*absPath*) uzunluğu *MaxLength*'ten büyükse, işlev **null**değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Fullpath** Işlevi, *RelPath* 'teki göreli yol adını tam nitelikli veya mutlak yoluna genişletir ve bu adı *absPath*olarak depolar. *AbsPath* **null**ise, yol adını tutmak için yeterli uzunlukta bir arabellek ayırmak üzere **malloc** kullanılır. Bu arabelleği serbest bırakmak için çağıranın sorumluluğundadır. Göreli yol adı geçerli konumdan başka bir konumun yolunu belirtir (örneğin, geçerli çalışma dizini: "."). Mutlak yol adı, dosya sisteminin kökünden istenen konuma ulaşmak için gereken yolun tamamını belirten göreli bir yol adının genişletmesinin bir yoludur. **_Makepath**farklı olarak, **_fullpath** "./" veya "Içeren göreli yollar (*RelPath*) için mutlak yol adı elde etmek üzere kullanılabilir. /"adında.

Örneğin, C çalışma zamanı yordamlarını kullanmak için, uygulamanın, yordamlar için bildirimleri içeren üst bilgi dosyalarını içermesi gerekir. Her üstbilgi dosyası include deyimleri, dosyanın konumunu göreli bir şekilde (uygulamanın çalışma dizininden) başvurur:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <stdlib.h>
```

dosyanın mutlak yolu (gerçek dosya sistemi konumu) şu şekilde olabilir:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini kullanımda olan çok baytlı kod sayfasına göre tanıyor. **_wfullpath** , **_fullpath**geniş karakterli bir sürümüdür; **_wfullpath** dize bağımsız değişkenleri geniş karakterli dizelerdir. **_wfullpath** ve **_fullpath** , **_wfullpath** çok baytlı karakter dizelerini işleyememesi dışında aynı şekilde davranır.

**_DEBUG** ve **_CRTDBG_MAP_ALLOC** her ikisi de tanımlıysa, **_fullpath** ve **_wfullpath** çağrıları, bellek ayırmalarının hata ayıklamasına izin vermek için **_fullpath_dbg** ve **_wfullpath_dbg** çağrılarıyla değiştirilmiştir. Daha fazla bilgi için bkz. [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Bu işlev, *maxlen* değeri 0 ' dan küçük veya buna eşit Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **null**değerini döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

*AbsPath* arabelleği **null**ise **_fullpath** , bir arabellek ayırmak ve *MaxLength* bağımsız değişkenini yok saymaya yönelik [malloc](malloc.md) çağırır. Bu arabelleği serbest bırakma sorumluluğu ( [ücretsiz](free.md)kullanılarak) uygun şekilde. *RelPath* bağımsız değişkeni bir disk sürücüsü belirtiyorsa, bu sürücünün geçerli dizini yol ile birleştirilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath**|\<Stdlib. h>|
|**_wfullpath**|\<Stdlib. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
