---
title: _get_fmode
ms.date: 4/2/2020
api_name:
- _get_fmode
- _o__get_fmode
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
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: fbaa30d0842400037f37508df94726f3e7fd7090
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345164"
---
# <a name="_get_fmode"></a>_get_fmode

Dosya G/Ç işlemleri için varsayılan dosya çeviri modunu alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>Parametreler

*pmode*<br/>
Geçerli varsayılan modla doldurulacak bir tamsayı işaretçisi: **_O_TEXT** veya **_O_BINARY.**

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır döndürür; hata bir hata kodu. *Pmode* **NULL**ise, geçersiz parametre işleyicisi [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

[İşlev, _fmode](../../c-runtime-library/fmode.md) global değişkenin değerini alır. Bu değişken, **_open,** **_pipe,** **fopen**ve [freopen](freopen-wfreopen.md)gibi hem düşük düzeyli hem de akış dosyası G/Ç işlemleri için varsayılan dosya çeviri modunu belirtir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_set_fmode'daki](set-fmode.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Metin ve İkili Mod Dosya I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
