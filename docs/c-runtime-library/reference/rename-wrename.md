---
title: Yeniden Adlandır, _wrename | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f02829b394649b86dfda9baad7c5792853fce746
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407479"
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

*EskiAd*<br/>
Eski adı işaretçi.

*newname*<br/>
Yeni ad işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bu işlevlerin her biri 0 döndürür. Bir hata üzerinde işlevi sıfır olmayan bir değer döndürür ve ayarlar **errno** aşağıdaki değerlerden birine:

|errno değeri|Koşul|
|-|-|
**EACCES**|Dosya veya dizin tarafından belirtilen *newname* zaten var veya (geçersiz bir yol) oluşturulamadı; veya *EskiAd* bir dizindir ve *newname* farklı bir yol belirtir.
**ENOENT**|Dosya veya tarafından belirtilen yol *EskiAd* bulunamadı.
**EINVAL**|Adı geçersiz karakterler içeriyor.

Diğer olası dönüş değerleri için bkz: [_doserrno, _errno, syserrlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Yeniden adlandırma** işlevi yeniden adlandırır dosya veya dizin tarafından belirtilen *EskiAd* tarafından verilen adına *newname*. Eski adı, varolan bir dosya veya dizin yolunu olması gerekir. Varolan bir dosya veya dizin adını yeni bir ad olmamalıdır. Kullanabileceğiniz **yeniden adlandırma** bir dosyayı bir dizin veya aygıtı farklı bir yol vererek diğerine taşıma *newname* bağımsız değişkeni. Ancak, kullanamazsınız **yeniden adlandırma** bir dizin taşımak için. Dizinleri yeniden adlandırıldı ancak taşınmaz.

**_wrename** bir joker karakter sürümü **_rename**; bağımsız değişkenleri **_wrename** joker karakter dizelerdir. **_wrename** ve **_rename** Aksi takdirde aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_trename**|**Yeniden Adlandır**|**Yeniden Adlandır**|**_wrename**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Yeniden Adlandır**|\<io.h > veya \<stdio.h >|
|**_wrename**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
