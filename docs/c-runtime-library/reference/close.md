---
title: _close
ms.date: 11/04/2016
api_name:
- _close
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: e274cd45c42a5cf49430ecce69e111cbbf6fe88b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942930"
---
# <a name="_close"></a>_close

Bir dosyayı kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık dosyaya başvuran dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

**_close** dosya başarıyla kapatılmışsa 0 döndürür. -1 ' in dönüş değeri bir hatayı gösterir.

## <a name="remarks"></a>Açıklamalar

**_Close** işlevi *FD*ile ilişkili dosyayı kapatır.

Dosya tanımlayıcısı ve temel alınan işletim sistemi dosya tanıtıcısı kapalıdır. Bu nedenle, dosya başlangıçta bir **Win32 işlevi kullanılarak** açıldıysa ve **_open_osfhandle**kullanarak bir dosya tanımlayıcısına dönüştürülürse, **CloseHandle** çağrısı yapmak gerekli değildir.

Bu işlev, parametrelerini doğrular. *FD* hatalı bir dosya tanımlayıcısıdır, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlevler-1 döndürür ve **errno** , **EBADF**olarak ayarlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_close**|\<GÇ. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Open](open-wopen.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
