---
title: _setmaxstdio
ms.date: 11/04/2016
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
ms.openlocfilehash: 58cffedf673e23a69c2d8040071b2e3353ff4502
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445090"
---
# <a name="setmaxstdio"></a>_setmaxstdio

En fazla eşzamanlı olarak açık dosyaları sayısı ayarlar **stdio** düzeyi.

## <a name="syntax"></a>Sözdizimi

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>Parametreler

*newmax*<br/>
Yeni aynı anda açık dosya sayısı üst sınırı **stdio** düzeyi.

## <a name="return-value"></a>Dönüş Değeri

Döndürür *newmax* başarılıysa; Aksi takdirde -1.

Varsa *newmax* olduğu küçüktür **_IOB_ENTRIES** ya da açıklandığı gibi geçersiz parametre işleyicisi işletim sisteminde kullanılamıyor sayısı çağrılır büyük [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Setmaxstdio** işlev aynı anda Aç olabilecek dosyaların sayısı, en fazla değeri değiştirir **stdio** düzeyi.

C çalışma zamanı g/ç Win32 platformları pek çok daha açık dosyalarda önceki sürümlerde artık desteklemektedir. 2.048 dosyaları kadar aynı anda açık olabilir [lowio düzeyi](../../c-runtime-library/low-level-i-o.md) (diğer bir deyişle, açtığınız ve yoluyla erişilen **_aç**, **_read**, **_write**, g/ç işlevler ailesini vb.). En fazla 512 dosyaları aynı anda açık olabilir [stdio düzeyi](../../c-runtime-library/stream-i-o.md) (diğer bir deyişle, açtığınız ve yoluyla erişilen **fopen**, **fgetc**, **fputc** İşlevler ailesini vb.). 512 açık dosyaları sınırını **stdio** düzeyini, en fazla yoluyla 2.048 artırılabilir **_setmaxstdio** işlevi.

Çünkü **stdio**-gibi işlevler, düzey **fopen**, üst kısmındaki yerleşik **lowio** işlevleri, en fazla 2.048, sabit bir üst sınırı sayısı için aynı anda C çalışma zamanı kitaplığı erişilen dosyalarını açın.

> [!NOTE]
> Bu üst sınırı belirli Win32 platform ve yapılandırma tarafından desteklenen özellikler olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: [_getmaxstdio](getmaxstdio.md) kullanma örneği için **_setmaxstdio**.

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
