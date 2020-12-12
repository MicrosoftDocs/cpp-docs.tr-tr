---
description: ': Towctrans hakkında daha fazla bilgi edinin'
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
ms.openlocfilehash: 7b8ecdd38ca45eb658d5e9f61bf05549878228bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318305"
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

*,*<br/>
Dönüştürmek istediğiniz karakter.

*alan*<br/>
[Wctrans](wctrans.md)'ın dönüş değerini içeren bir tanımlayıcı.

## <a name="return-value"></a>Dönüş Değeri

**Towctrans** öğesinden sonra *c* karakteri, *kategoride* dönüştürme kuralını kullandı.

## <a name="remarks"></a>Açıklamalar

*Kategori* değeri, [wctrans](wctrans.md)için daha önceki başarılı bir çağrı tarafından döndürülmelidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**towctrans**|\<wctype.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**Towctrans** kullanan bir örnek için bkz. **wctrans** .

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
