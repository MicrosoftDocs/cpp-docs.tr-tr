---
title: fclose, _fcloseall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fclose
- _fcloseall
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fclose
- _fcloseall
dev_langs:
- C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71b98a239cd1a6504611bf436533e7b5fbe1302c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall

Bir akış kapatır (**fclose**) veya tüm açık akışları kapatır (**_fcloseall**).

## <a name="syntax"></a>Sözdizimi

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fclose** akış başarıyla kapalıysa 0 döndürür. **_fcloseall** kapalı akış toplam sayısını döndürür. Her iki işlevi dönüş **EOF** hatayı belirtmek için.

## <a name="remarks"></a>Açıklamalar

**Fclose** işlev kapanır *akış*. Varsa *akış* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **fclose** ayarlar **errno** için **EINVAL** ve döndürür **EOF**. Önerilir *akış* işaretçi her zaman kontrol edileceği bu işlev çağrılmadan önce.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

**_Fcloseall** işlev kapatır dışında açık olan tüm akışlar **stdin**, **stdout**, **stderr** (ve, MS-DOS, **_stdaux**  ve **_stdprn**). Ayrıca kapatır ve tarafından oluşturulan geçici dosyalar siler **tmpfile**. Her iki işlevlerde akışı ile ilişkilendirilmiş tüm arabellekler kapatmadan önce temizlenir. Akış kapalıyken sistem tarafından ayrılmış arabellekleri yayınlanır. İle kullanıcı tarafından atanan arabellekleri **setbuf** ve **setvbuf** değil otomatik olarak yayımlanmıştır.

**Not:** bu işlevlerin bir akış kapatmak için kullanıldığında, temel alınan dosya tanımlayıcısı ve işletim sistemi dosya işleci (veya yuva), yanı sıra Akış kapalı. Bu nedenle, dosyayı ilk olarak açtıysanız bir dosya olarak işlemek veya dosya tanımlayıcısı ve ile kapalı **fclose**, değil de çağrı yapmanız **_close** için dosya tanımlayıcısı kapatın; Win32 işlevini çağırmayın  **CloseHandle** dosya tanıtıcısı kapatın.

**fclose** ve **_fcloseall** diğer iş parçacıklarından girişim karşı korumak için kodu ekleyin. Kilitleme sürüm için bir **fclose**, bkz: **_fclose_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fclose**|\<stdio.h >|
|**_fcloseall**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [fopen](fopen-wfopen.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
