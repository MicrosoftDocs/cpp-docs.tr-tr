---
title: kaldır, _wremove
ms.date: 11/04/2016
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
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
ms.openlocfilehash: 05f1c5b6760520e5a982777faa903b3c5116ad05
ms.sourcegitcommit: 22f7c4a9b4fc2158fb5283810f15275803cafe10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2019
ms.locfileid: "54417609"
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

*Yolu*<br/>
Kaldırılacak dosyanın yolu.

## <a name="return-value"></a>Dönüş Değeri

Dosya başarıyla silinirse bu işlevlerin her biri 0 döndürür. Aksi takdirde, -1 döndürür ve ayarlar **errno** ya da **SPAWN** yolunu salt okunur bir dosya belirtir belirtmek için bir dizini belirtir ya da dosya açıksa veya **ENOENT** Dosya adı veya yolu bulunamadı belirtmek için.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Kaldır** işlevi tarafından belirtilen dosya siler *yolu.* **_wremove** geniş karakterli sürümüdür **_kaldır**; *yolu* bağımsız değişkeni **_wremove** geniş karakterli bir dizedir. **_wremove** ve **_kaldır** aynı şekilde davranır. Silinebilmesi için önce tüm dosya tanıtıcıları kapatılmalıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**remove**|\<stdio.h > veya \<io.h >|
|**_wremove**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
