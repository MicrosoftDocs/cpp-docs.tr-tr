---
title: towctrans
ms.date: 11/04/2016
api_name:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- towctrans
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
ms.openlocfilehash: d63fc343647cd0f949f282e2a64d4a0636e62bd7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957432"
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
Dönüştürmek istediğiniz karakter.

*Kategori*<br/>
[Wctrans](wctrans.md)'ın dönüş değerini içeren bir tanımlayıcı.

## <a name="return-value"></a>Dönüş Değeri

**Towctrans** öğesinden sonra *c*karakteri, *kategoride*dönüştürme kuralını kullandı.

## <a name="remarks"></a>Açıklamalar

*Kategori* değeri, [wctrans](wctrans.md)için daha önceki başarılı bir çağrı tarafından döndürülmelidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**towctrans**|\<wctype. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**Towctrans**kullanan bir örnek için bkz. **wctrans** .

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
