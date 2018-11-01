---
title: yeniden adlandır, _wrename
ms.date: 11/04/2016
apiname:
- rename
- _wrename
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
- _wrename
- _trename
- Rename
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
ms.openlocfilehash: 70793dee54460b6372bfbe815115aa9211670c6f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463992"
---
# <a name="rename-wrename"></a>yeniden adlandır, _wrename

Bir dosya veya dizin yeniden adlandırın.

## <a name="syntax"></a>Sözdizimi

```C
int rename(
   const char *oldname,
   const char *newname
);
int _wrename(
   const wchar_t *oldname,
   const wchar_t *newname
);
```

### <a name="parameters"></a>Parametreler

*OldName*<br/>
Eski adı işaretçisi.

*Yeni ad*<br/>
Yeni ad işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarılı olursa 0 döndürür. Bir hatada, işlev sıfır olmayan bir değer döndürür ve ayarlar **errno** aşağıdaki değerlerden biri olarak:

|errno değeri|Koşul|
|-|-|
**SPAWN**|Dosya veya dizin tarafından belirtilen *newname* zaten var veya (geçersiz yol) oluşturulamadı; veya *oldname* bir dizin ve *newname* farklı bir yol belirtir.
**ENOENT**|Dosya veya yol tarafından belirtilen *oldname* nebyl nalezen.
**EINVAL**|Ad geçersiz karakterler içeriyor.

Diğer olası dönüş değerleri için bkz: [_doserrno, gt; _errno &, syserrlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Yeniden Adlandır** dosya veya dizin tarafından belirtilen işlevi yeniden adlandırır *oldname* tarafından verilen adına *newname*. Eski adı, varolan bir dosya veya dizin yolu olmalıdır. Yeni ad var olan bir dosya veya dizin adı olmalıdır. Kullanabileceğiniz **Yeniden Adlandır** bir dosya bir dizin veya cihaz farklı bir yol vererek taşımak için *newname* bağımsız değişken. Bununla birlikte kullanamazsınız **Yeniden Adlandır** bir dizine taşınır. Dizinleri yeniden adlandırılamaz ancak taşınmaz.

**_wrename** geniş karakterli sürümüdür **_rename**; bağımsız değişkenler **_wrename** geniş karakterli dizelerdir. **_wrename** ve **_rename** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**Yeniden adlandırma**|**Yeniden adlandırma**|**_wrename**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Yeniden adlandırma**|\<io.h > veya \<stdio.h >|
|**_wrename**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_renamer.c
/* This program attempts to rename a file named
* CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation
* to succeed, a file named CRT_RENAMER.OBJ must exist and
* a file named CRT_RENAMER.JBO must not exist.
*/

#include <stdio.h>

int main( void )
{
   int  result;
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";

   /* Attempt to rename file: */
   result = rename( old, new );
   if( result != 0 )
      printf( "Could not rename '%s'\n", old );
   else
      printf( "File '%s' renamed to '%s'\n", old, new );
}
```

### <a name="output"></a>Çıkış

```Output
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
