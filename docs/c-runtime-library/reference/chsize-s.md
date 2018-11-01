---
title: _chsize_s
ms.date: 11/04/2016
apiname:
- _chsize_s
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
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: a56efe826d43c80dc2cdee295e58872e7dd3c9ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597606"
---
# <a name="chsizes"></a>_chsize_s

Bir dosyanın boyutunu değiştirir. Bu bir sürümüdür [_chsize](chsize.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık olan bir dosyaya başvuran dosya tanımlayıcısı.

*Boyutu*<br/>
Yeni dosyanın bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_chsize_s** dosya boyutu başarıyla değiştirilirse, 0 değerini döndürür. Sıfır dışında bir dönüş değeri bir hata olduğunu gösterir: dönüş değeri **SPAWN** belirtilen dosyaya erişime karşı kilitliyse **EBADF** tanımlayıcısı geçersiz veya belirtilen dosya salt okunur **ENOSPC** boşluk cihazda bırakılırsa veya **EINVAL** boyutu küçükse sıfır. **errno** aynı değere ayarlanır.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Chsize_s** işlevini genişletir veya ilişkili dosya keser *fd* tarafından belirtilen uzunluktan *boyutu*. Dosya yazma izin veren bir modda açık olmalıdır. Dosya uzatıldıysa null karakterleri ('\0') eklenir. Dosya kesilmiş, özgün dosya uzunluğu kısaltılmış dosyanın sonundan tüm veriler kaybolur.

**_chsize_s** bir 64-bit tamsayı olarak dosyanın boyutunu alır ve bu nedenle, dosya boyutu 4 GB'den büyük başa çıkabilir. **_chsize** 32-bit dosya boyutlarına sınırlıdır.

Bu işlev, parametrelerini doğrular. Varsa *fd* geçerli dosya tanımlayıcısı veya boyutu sıfırdan küçüktür, geçersiz parametre işleyicisi çağrılır, açıklandığı değil [Parameter Validation](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
