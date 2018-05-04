---
title: towctrans | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9d70570339868feb62ee906a707cf16ca03d556
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="towctrans"></a>towctrans

Bir karakter dönüştürür.

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
Dönüş değerini içeren bir tanımlayıcı [wctrans](wctrans.md).

## <a name="return-value"></a>Dönüş Değeri

Karakter *c*, sonra **towctrans** dönüştürme kuralda kullanılan *kategori*.

## <a name="remarks"></a>Açıklamalar

Değeri *kategori* başarılı bir önceki çağrısı tarafından Döndürülmüş gerekir [wctrans](wctrans.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**towctrans**|\<wctype.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: **wctrans** kullanan bir örnek için **towctrans**.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
