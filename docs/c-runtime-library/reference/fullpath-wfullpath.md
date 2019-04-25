---
title: _fullpath, _wfullpath
ms.date: 11/04/2016
apiname:
- _fullpath
- _wfullpath
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
ms.openlocfilehash: aeacaf581b7f33ee893754c192ae547376ce73ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287648"
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath

Belirtilen göreli yol adı için bir mutlak ya da tam yol adı oluşturur.

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
Mutlak ya da tam yol adını içeren bir arabellek için işaretçi veya **NULL**.

*relPath*<br/>
Göreli yol adı.

*maxLength*<br/>
Mutlak yol adı arabelleği uzunluğu en fazla (*absPath*). Bu süre için bayt cinsinden olduğunu **_fullpath** ancak geniş karakterler (**wchar_t**) için **_wfullpath**.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri mutlak yol adını içeren bir arabelleği için bir işaretçi döndürür (*absPath*). Bir hata varsa (örneğin, değer iletilmezse *relPath* geçersiz veya bulunamıyor, bir sürücü harfini içeren veya oluşturulan mutlak yol adının uzunluğu (*absPath*) büyüktür: *maxLength*), işlev döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fullpath** işlevini genişletir. göreli yol adlarında *relPath* tam veya mutlak yolunu ve bu ad depoları *absPath*. Varsa *absPath* olduğu **NULL**, **malloc** yol adı tutmak için yeterli uzunlukta bir arabellek ayırmak için kullanılır. Çağıranın bu arabellek ücretsiz sorumluluğundadır. Bir göreli yol adı başka bir konuma bir yolu, geçerli konumdan belirtir. (geçerli çalışma dizini gibi: "."). Genişleme dosya sisteminin kök istenen konumu erişmek için gerekli tüm yol bildiren bir göreli yol adının bir mutlak yol adıdır. Farklı **_makepath**, **_fullpath** göreli yollar için mutlak yol adını almak için kullanılabilir (*relPath*) içeren ". /"veya".. / "adlarında.

Örneğin, C çalışma zamanı yordamları kullanmak için uygulama bildirimleri için rutinleri içeren üst bilgi dosyaları içermelidir. Her üst bilgi dosyası (Uygulama Çalışma dizininden) göreli bir şekilde dosyasının konumunu deyimi başvuruları içerir:

```C
#include <stdlib.h>
```

ne zaman dosyanın mutlak yolu (gerçek dosya sistemi konumundan) olabilir:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak işler. **_wfullpath** geniş karakterli sürümüdür **_fullpath**; dize bağımsız değişkenleri **_wfullpath** geniş karakterli dizelerdir. **_wfullpath** ve **_fullpath** aynı şekilde davranır **_wfullpath** çok baytlı karakter dizelerini işlemez.

Varsa **_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanmış olan iki çağrıları **_fullpath** ve **_wfullpath** çağrılarıyladeğiştirilir **_fullpath_dbg** ve **_wfullpath_dbg** bellek ayırmaları hata ayıklama için izin vermek için. Daha fazla bilgi için [_fullpath_dbg, _wfullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md), *maxlen* 0 küçük veya ona eşit. Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **NULL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Varsa *absPath* arabellek **NULL**, **_fullpath** çağrıları [malloc](malloc.md) bir arabelleği ayrılamadı ve yoksayar *maxLength*  bağımsız değişken. Bu arabellek ayırması için çağıranın sorumluluğu olan (kullanarak [ücretsiz](free.md)) uygun şekilde. Varsa *relPath* bağımsız değişkeni belirtir bir disk sürücüsü, bu sürücünün geçerli dizin yolu ile birleştirilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h >|
|**_wfullpath**|\<stdlib.h > veya \<wchar.h >|

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
