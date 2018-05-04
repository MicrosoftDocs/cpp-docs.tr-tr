---
title: Kaldır, _wremove | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wremove
- remove
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
- remove
- _wremove
- _tremove
dev_langs:
- C++
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36cdc09107a66067b358cb2fd72ec9bd1b2b30a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="remove-wremove"></a>kaldır, _wremove

Bir dosyayı silin.

## <a name="syntax"></a>Sözdizimi

```C
int remove(
   const char *path
);
int _wremove(
   const wchar_t *path
);
```

### <a name="parameters"></a>Parametreler

*Yol*<br/>
Kaldırılacak dosyanın yolu.

## <a name="return-value"></a>Dönüş Değeri

Dosya başarıyla silinirse bu işlevlerin her biri 0 döndürür. Aksi takdirde, -1 döndürür ve ayarlar **errno** ya da **EACCES** salt okunur bir dosya yolunu belirtir veya dosya açıksa belirtmek üzere veya **ENOENT** belirtmek için Dosya adı veya yolu bulunamadı veya yol bir dizin belirtir.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer dönüş kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Kaldırmak** işlevi tarafından belirtilen dosyayı siler *yolu.* **_wremove** bir joker karakter sürümü **_remove**; *yolu* bağımsız değişkeni **_wremove** bir joker karakter dizesidir. **_wremove** ve **_remove** Aksi takdirde aynı şekilde davranır. Silinebilmesi için önce bir dosyaya tüm tanıtıcıları kapatılmalıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**remove**|\<stdio.h > veya \<io.h >|
|**_wremove**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_remove.c
/* This program uses remove to delete crt_remove.txt */

#include <stdio.h>

int main( void )
{
   if( remove( "crt_remove.txt" ) == -1 )
      perror( "Could not delete 'CRT_REMOVE.TXT'" );
   else
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );
}
```

### <a name="input-crtremovetxt"></a>Giriş: crt_remove.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
