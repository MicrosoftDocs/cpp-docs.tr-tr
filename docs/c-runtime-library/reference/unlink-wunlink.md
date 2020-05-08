---
title: _unlink, _wunlink
ms.date: 4/2/2020
api_name:
- _unlink
- _wunlink
- _o__unlink
- _o__wunlink
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
- _tunlink
- _unlink
- wunlink
- _wunlink
helpviewer_keywords:
- files [C++], deleting
- _wunlink function
- wunlink function
- unlink function
- _unlink function
- tunlink function
- files [C++], removing
- _tunlink function
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
ms.openlocfilehash: af6fd6c7065529b43f5e275ce1d745d0031ddfb7
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909287"
---
# <a name="_unlink-_wunlink"></a>_unlink, _wunlink

Bir dosyayı silin.

## <a name="syntax"></a>Sözdizimi

```C
int _unlink(
   const char *filename
);
int _wunlink(
   const wchar_t *filename
);
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Kaldırılacak dosyanın adı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarılıysa 0 döndürür. Aksi takdirde, işlev-1 döndürür ve **errno** değerini **EACCES**olarak ayarlar. Bu, yolun bir salt okunurdur dosya ya da dizin belirttiği **ya da bir**dosyanın veya yolun bulunamadığı anlamına gelir.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**_Unlink** işlevi *filename*tarafından belirtilen dosyayı siler. **_wunlink** , **_unlink**geniş karakterli bir sürümüdür; _wunlink *dosya adı* bağımsız **_wunlink** değişkeni, geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tunlink**|**_unlink**|**_unlink**|**_wunlink**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_unlink**|\<GÇ. h> ve \<stdio. h>|
|**_wunlink**|\<GÇ. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="code-example"></a>Kod Örneği

Bu program CRT_UNLINK silmek için _unlink kullanır. TXT.

```C
// crt_unlink.c

#include <stdio.h>

int main( void )
{
   if( _unlink( "crt_unlink.txt" ) == -1 )
      perror( "Could not delete 'CRT_UNLINK.TXT'" );
   else
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );
}
```

### <a name="input-crt_unlinktxt"></a>Giriş: crt_unlink. txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Deleted 'CRT_UNLINK.TXT'
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[remove, _wremove](remove-wremove.md)<br/>
