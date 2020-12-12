---
description: 'Hakkında daha fazla bilgi edinin: _chsize_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b3fa28923b558dc9b396cffc3418ff679349000d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253097"
---
# <a name="_chsize_s"></a>_chsize_s

Bir dosyanın boyutunu değiştirir. Bu, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_chsize](chsize.md) bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Açık bir dosyaya başvuran dosya tanımlayıcısı.

*boyutla*<br/>
Dosyanın bayt cinsinden yeni uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_chsize_s** , dosya boyutu başarıyla değiştirilmişse 0 değerini döndürür. Sıfır olmayan bir dönüş değeri bir hatayı gösterir: belirtilen dosya salt  okunurdur veya tanımlayıcı **geçersiz ise,** belirtilen dosya salt okunurdur veya tanımlayıcı geçersizse, bir boşluk, cihazda boş alan yoksa **enospc** , veya boyut sıfırdan küçükse, **EINVAL** . **errno** değeri aynı değere ayarlandı.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Chsize_s** işlevi *FD* ile ilişkili dosyayı *boyutuna* göre belirtilen uzunluğa genişletir veya keser. Dosyanın yazmaya izin veren bir modda açık olması gerekir. Dosya genişletilmişse null karakterler (' \ 0 ') eklenir. Dosya kesilmişse, kısaltılmış dosyanın sonundaki tüm veriler dosyanın özgün uzunluğuna kaybedilir.

**_chsize_s** dosya boyutu olarak 64 bitlik bir tamsayı alır ve bu nedenle 4 GB 'tan büyük dosya boyutlarını işleyebilir. **_chsize** , 32 bitlik dosya boyutları ile sınırlıdır.

Bu işlev, parametrelerini doğrular. *FD* geçerli bir dosya tanımlayıcısı değil veya boyut sıfırdan küçükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
