---
title: kaldır, _wremove
ms.date: 4/2/2020
api_name:
- _wremove
- remove
- _o__wremove
- _o_remove
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
ms.openlocfilehash: 6a3d7ea81b2f6b1a7e87c706ca883394e02dff3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338144"
---
# <a name="remove-_wremove"></a>kaldır, _wremove

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
Dosyanın yolu kaldırılacak.

## <a name="return-value"></a>Dönüş Değeri

Dosya başarıyla silinirse, bu işlevlerin her biri 0 döndürür. Aksi takdirde, -1 döndürür ve **eacces'e** **errno'yu** ayarlayıp, yolun salt okunur dosyayı belirttiğini, bir dizini belirlediğini veya dosyanın açık olduğunu veya dosya adının veya yolun bulunamadığını belirtmek için **ENOENT'e** ayarlar.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**Kaldırma** *işlevi, yol* tarafından belirtilen dosyayı siler. **_wremove** **_remove**geniş karakterli bir versiyonudur; **_wremove** *yol* bağımsız değişkeni geniş karakterli bir dizedir. **_wremove** ve **_remove** aynı şekilde davranan. Bir dosyanın silinemeden önce tüm tutamaçlarının kapatılması gerekir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**remove**|\<stdio.h> \<veya io.h>|
|**_wremove**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

### <a name="input-crt_removetxt"></a>Giriş: crt_remove.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
