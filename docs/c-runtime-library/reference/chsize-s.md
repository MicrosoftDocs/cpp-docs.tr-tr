---
title: _chsize_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8867761f644e1367c3ab1101a9a5860b9cfc9c33
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="chsizes"></a>_chsize_s

Dosyasının boyutu değişir. Bu bir sürümüdür [_chsize](chsize.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık olan bir dosyaya başvuruda bulunan dosya tanımlayıcısı.

*Boyutu*<br/>
Yeni dosyanın bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_chsize_s** dosya boyutu başarıyla değiştirilirse 0 değerini döndürür. Sıfır olmayan bir dönüş değeri bir hata gösterir: dönüş değeri **EACCES** belirtilen dosya erişime karşı kilitliyse **EBADF** belirtilen dosya salt okunur ise veya tanımlayıcısı geçersiz **ENOSPC** boşluk cihazda bırakılırsa veya **EINVAL** boyutu küçükse sıfır. **errno** aynı değere ayarlanır.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Chsize_s** işlevi genişletir veya ilişkili dosya kesen *fd* tarafından belirtilen uzunluğa *boyutu*. Dosya yazma izin veren bir modda açık olması gerekir. Boş karakterler ('\0') dosya genişletilmişse eklenir. Dosya kesilirse, dosyanın özgün uzunluğu kısaltılmış dosyasının sonuna tüm veriler kaybolur.

**_chsize_s** dosya boyutu 64 bitlik bir tamsayı alır ve bu nedenle dosya boyutu 4 GB'den büyük işleyebilir. **_chsize** 32-bit dosya boyutlarına sınırlıdır.

Bu işlev parametrelerini doğrular. Varsa *fd* geçerli dosya tanımlayıcısı veya boyutu sıfırdan küçük, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi değil [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
