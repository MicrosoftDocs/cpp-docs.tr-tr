---
title: towctrans
ms.date: 11/04/2016
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: b814c65d2f5d0bb18b19d97a539d79dd6df8a1c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561414"
---
# <a name="towctrans"></a>towctrans

Bir karakteri dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
wint_t towctrans(
   wint_t c,
   wctrans_t category
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürmek istediğiniz karakterdir.

*Kategori*<br/>
Dönüş değeri içeren bir tanımlayıcı [wctrans](wctrans.md).

## <a name="return-value"></a>Dönüş Değeri

Karakter *c*, sonra **towctrans** dönüştürme kuralda kullanılan *kategori*.

## <a name="remarks"></a>Açıklamalar

Değerini *kategori* başarılı bir önceki çağrı tarafından iade edilmiş gerekir [wctrans](wctrans.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**towctrans**|\<wctype.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: **wctrans** kullanan bir örnek için **towctrans**.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
