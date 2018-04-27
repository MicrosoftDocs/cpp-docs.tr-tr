---
title: towctrans | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1e3029fc9d33df93e13e6fd0a8e9e8d8da168b0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
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
