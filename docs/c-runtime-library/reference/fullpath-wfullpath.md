---
title: _fullpath, _wfullpath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b472987b0cac41c57e5fd22b2eedecef522613b4
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath

Belirtilen göreli yol adı için bir mutlak veya tam yol adı oluşturur.

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
Mutlak veya tam yol adını içeren bir arabellek işaretçi veya **NULL**.

*relPath*<br/>
Göreli yol adı.

*maxLength*<br/>
Mutlak bir yol adı arabelleği maksimum uzunluğu (*absPath*). Bu uzunluğudur için bayt cinsinden **_fullpath** ancak geniş karakterler (**wchar_t**) için **_wfullpath**.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir işaretçi mutlak yol adı içeren bir arabellek döndürür (*absPath*). Bir hata varsa (örneğin, değer olarak aktarılırsa *relPath* geçersiz veya bulunamıyor, bir sürücü harfi içerir veya oluşturulan mutlak bir yol adının uzunluğu (*absPath*) büyüktür: *maxLength*), işlevi döndürür **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fullpath** işlevi genişletir göreli yol adındaki *relPath* tam olarak nitelenmiş veya mutlak bir yol ve bu ad depoları *absPath*. Varsa *absPath* olan **NULL**, **malloc** yol adını tutmak için yeterli uzunlukta bir arabellek ayırmak için kullanılır. Çağıranın bu arabelleği serbest sorumluluğundadır. Bir göreli yol adı bir yol başka bir konuma geçerli konumu belirtir (geçerli çalışma dizini gibi: "."). Genişleme dosya sisteminin kök istenen konumu erişmek için gerekli yolun tamamını bildiren bir göreli yol adının bir mutlak yol adıdır. Farklı **_makepath**, **_fullpath** göreli yollar için mutlak bir yol adı almak için kullanılabilir (*relPath*) içeren ". /"veya".. / "adlarında.

Örneğin, C çalışma zamanı yordamları kullanmak için uygulama yordamları için bildirimleri içeren üstbilgi dosyaları içermelidir. Her üstbilgi dosyası göreli bir şekilde (dizininden uygulamanın çalışma) dosyasının konumunu deyimi başvurular içerir:

```C
#include <stdlib.h>
```

ne zaman dosyasının (gerçek dosya sistemi konumu) mutlak yolu olabilir:

`\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h`

**_fullpath** şu anda kullanımda birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. **_wfullpath** bir joker karakter sürümü **_fullpath**; dize bağımsız değişkenleri **_wfullpath** joker karakter dizelerdir. **_wfullpath** ve **_fullpath** durumlar dışında aynı şekilde davranır **_wfullpath** çok baytlı karakter dizeleri işlemez.

Varsa **_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanmış olan iki çağrıları **_fullpath** ve **_wfullpath** yapılançağrılartarafındandeğiştirilen **_fullpath_dbg** ve **_wfullpath_dbg** bellek ayırmaları hata ayıklama için izin vermek için. Daha fazla bilgi için bkz: [_wfullpath_dbg olan _fullpath_dbg](fullpath-dbg-wfullpath-dbg.md).

Bu işlev geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), *maxlen* 0 küçük veya eşit. Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **NULL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath**|**_fullpath**|**_fullpath**|**_wfullpath**|

Varsa *absPath* arabellek **NULL**, **_fullpath** çağrıları [malloc](malloc.md) arabellek ayıramadı ve yoksayar *maxLength*  bağımsız değişkeni. Bu arabellek ayırması için çağıranın sorumluluğu olan (kullanarak [ücretsiz](free.md)) uygun şekilde. Varsa *relPath* bağımsız değişkeni bir disk sürücüsü belirtir, bu sürücünün geçerli dizin yolu ile birleştirilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fullpath**|\<stdlib.h >|
|**_wfullpath**|\<stdlib.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
