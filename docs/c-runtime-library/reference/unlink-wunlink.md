---
title: _unlink, _wunlink
ms.date: 11/04/2016
api_name:
- _unlink
- _wunlink
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
ms.openlocfilehash: 878a1b4aa009bc8528dfac1908ed26c7e3b269ae
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957384"
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

*kısaltın*<br/>
Kaldırılacak dosyanın adı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarılıysa 0 döndürür. Aksi takdirde, işlev-1 döndürür ve **errno** değerini **EACCES**olarak ayarlar. Bu, yolun bir salt okunurdur dosya ya da dizin belirttiği **ya da bir**dosyanın veya yolun bulunamadığı anlamına gelir.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**_Kaldır** işlevi dosya *adı*tarafından belirtilen dosyayı siler. **_wbağını** kaldırma, **_//kaldır**; **_wbağını** kaldırma için *filename* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler, aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tunlink**|**_bağlantıyı kaldır**|**_bağlantıyı kaldır**|**_wbağını kaldır**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_bağlantıyı kaldır**|\<GÇ. h > ve \<stdio. h >|
|**_wbağını kaldır**|\<GÇ. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="code-example"></a>Kod Örneği

Bu program, CRT_UNLINK silmek için _bağlantıyı kaldır 'ı kullanır. TXT.

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[remove, _wremove](remove-wremove.md)<br/>
