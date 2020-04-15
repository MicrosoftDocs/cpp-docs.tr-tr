---
title: _chsize_s
ms.date: 4/2/2020
api_name:
- _chsize_s
- _o__chsize_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: 70845124eb889d73a0f87aadd923e2d86db96c29
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350083"
---
# <a name="_chsize_s"></a>_chsize_s

Dosyanın boyutunu değiştirir. Bu, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahip [_chsize](chsize.md) bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>Parametreler

*Fd*<br/>
Dosya tanımlayıcısı açık bir dosyaya atıfta.

*Boyutu*<br/>
Baytlar halindedosyanın yeni uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**dosya** boyutu başarıyla değiştirilirse _chsize_s değeri 0 döndürür. Sıfır olmayan bir iade değeri bir hatayı gösterir: belirtilen dosya erişime karşı kilitlenirse iade değeri **EACCES,** belirtilen dosya salt okunursa veya tanımlayıcı geçersizse **EBADF,** aygıtta boşluk kalmamışsa **ENOSPC** veya boyut sıfırdan küçükse **EINVAL** değeridir. **errno** aynı değere ayarlanır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_chsize_s** işlevi, *fd* ile ilişkili dosyayı *boyut olarak*belirtilen uzunluğa kadar genişletir veya kesilir. Dosya, yazmaya izin veren bir modda açık olmalıdır. Dosya genişletilirse null karakterleri ('\0') eklenir. Dosya kesilirse, kısaltılmış dosyanın sonundan dosyanın özgün uzunluğuna kadar olan tüm veriler kaybolur.

**_chsize_s** dosya boyutu olarak 64 bit tamsayı alır ve bu nedenle 4 GB'dan büyük dosya boyutlarını işleyebilir. **_chsize** 32 bit dosya boyutlarıyla sınırlıdır.

Bu işlev parametrelerini doğrular. *fD* geçerli bir dosya tanımlayıcısı değilse veya boyutu sıfırdan küçükse, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
