---
title: _filelength, _filelengthi64
ms.date: 4/2/2020
api_name:
- _filelengthi64
- _filelength
- _o__filelength
- _o__filelengthi64
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _filelength
- _filelengthi64
- filelengthi64
helpviewer_keywords:
- filelengthi64 function
- lengths, file
- filelength function
- _filelength function
- files [C++], length
- _filelengthi64 function
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
ms.openlocfilehash: 5fea019591fc5a90aab07f0347aa3f02fe0d43f3
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910214"
---
# <a name="_filelength-_filelengthi64"></a>_filelength, _filelengthi64

Bir dosyanın uzunluğunu alır.

## <a name="syntax"></a>Sözdizimi

```C
long _filelength(
   int fd
);
__int64 _filelengthi64(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Dosya tanımlayıcısını hedefleyin.

## <a name="return-value"></a>Dönüş Değeri

Hem **_filelength** hem de **_filelengthi64** , *FD*ile ilişkili hedef dosyanın bayt cinsinden dosya uzunluğunu döndürür. *FD* geçersiz bir dosya tanımlayıcısıdır, bu Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, her iki işlev de bir hatayı belirtmek için-1L döndürür ve **errno** 'U **EBADF**olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_filelength**|\<GÇ. h>|
|**_filelengthi64**|\<GÇ. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Chsize](chsize.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_fileno](fileno.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_stat, _wstat Işlevleri](stat-functions.md)<br/>
