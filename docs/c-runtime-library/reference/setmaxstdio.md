---
title: _setmaxstdio
ms.date: 05/21/2019
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
ms.openlocfilehash: 94b768d920ffd86a5bd762f8994244dda67fb15f
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174827"
---
# <a name="setmaxstdio"></a>_setmaxstdio

Aynı anda açık dosya sayısı için en fazla akış g/ç düzeyini ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int _setmaxstdio(
   int new_max
);
```

### <a name="parameters"></a>Parametreler

*new_max*<br/>
Yeni maksimum sayısı için aynı anda akış g/ç düzeyi dosyalarını açın.

## <a name="return-value"></a>Dönüş Değeri

Döndürür *new_max* başarılıysa; Aksi takdirde -1.

Varsa *new_max* olduğu küçüktür **_IOB_ENTRIES**, veya en fazla sayısından büyük işletim sistemi içinde kullanılabilir işler, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Setmaxstdio** işlev aynı anda akış g/ç düzeyi açık olabilir dosyaların sayısı, en fazla değeri değiştirir.

Artık, aynı anda açık 8192 dosyaları kadar destekler C çalışma zamanı g/ç [düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md). Bu düzeyde açılır ve kullanılarak erişilen dosyalar içerir **_aç**, **_read**, ve **_write** g/ç işlevler ailesini. Varsayılan olarak, en çok 512 dosyaları aynı anda açılabilir [g/ç düzeyi akış](../../c-runtime-library/stream-i-o.md). Bu düzeyde açılır ve kullanılarak erişilen dosyalar içerir **fopen**, **fgetc**, ve **fputc** işlevler ailesini. Akış g/ç düzeyinde 512 açık dosyalar sınırını kullanarak olmak üzere 8.192 maksimum kadar artırılabilir **_setmaxstdio** işlevi.

Akış miyim/O-düzeyi, gibi gördüğünden **fopen**, oluşturulan düşük miyim/O-düzey işlevleri en üstünde olmak üzere 8.192 maksimum C çalışma zamanı kitaplığı erişilen aynı anda açık dosya sayısı için sabit bir üst sınır olan.

> [!NOTE]
> Bu üst sınırı, belirli Win32 platform ve yapılandırma tarafından desteklenen özellikler dışında olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: [_getmaxstdio](getmaxstdio.md) kullanma örneği için **_setmaxstdio**.

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
