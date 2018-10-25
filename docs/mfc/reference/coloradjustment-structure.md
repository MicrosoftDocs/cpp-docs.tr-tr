---
title: COLORADJUSTMENT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 682bbe2e9a4987ca30614e9210198193de977e3e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066298"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT Yapısı

`COLORADJUSTMENT` Yapısını tanımlayan Windows tarafından kullanılan rengi ayarlama değerleri `StretchBlt` ve `StretchDIBits` işlevleri olduğunda `StretchBlt` noktalı modudur.

## <a name="syntax"></a>Sözdizimi

```
typedef struct  tagCOLORADJUSTMENT {    /* ca */
    WORD caSize;
    WORD caFlags;
    WORD caIlluminantIndex;
    WORD caRedGamma;
    WORD caGreenGamma;
    WORD caBlueGamma;
    WORD caReferenceBlack;
    WORD caReferenceWhite;
    SHORT caContrast;
    SHORT caBrightness;
    SHORT caColorfulness;
    SHORT caRedGreenTint;
} COLORADJUSTMENT;
```

#### <a name="parameters"></a>Parametreler

*caSize*<br/>
Yapının boyutunu bayt cinsinden belirtir.

*caFlags*<br/>
Çıkış görüntünün nasıl hazırlanmalı belirtir. Bu üye için NULL ya da aşağıdaki değerlerden herhangi bir birleşimini ayarlayabilirsiniz:

- CA_NEGATIVE eksi işareti orijinal görüntünün görüntüleneceğini belirtir.

- Son çıkış renkleri yoğunluğunu için logaritmik işlevi uygulanmalıdır CA_LOG_FILTER belirtir. Aydınlatma düşük olduğunda bu renk karşıtlığı artırır.

*caIlluminantIndex*<br/>
Resim nesnesi görüntülendiği ışık kaynağına renginin belirtir. Bu üye aşağıdaki değerlerden birine ayarlanabilir:

- ILLUMINANT_EQUAL_ENERGY

- ILLUMINANT_A

- ILLUMINANT_B

- ILLUMINANT_C

- ILLUMINANT_D50

- ILLUMINANT_D55

- ILLUMINANT_D65

- ILLUMINANT_D75

- ILLUMINANT_F2

- ILLUMINANT_TURNGSTEN

- ILLUMINANT_DAYLIGHT

- ILLUMINANT_FLUORESCENT

- ILLUMINANT_NTSC

*caRedGamma*<br/>
Kaynak rengin kırmızı birincil n. power gama düzeltmesi değeri belirtir. Değeri 2.500 65,000 için aralığında olması gerekir. 10.000 değerini gama düzeltmesi anlamına gelir.

*caGreenGamma*<br/>
Yeşil birincil kaynak renkler n. power gama düzeltmesi değerini belirtir. Değeri 2.500 65,000 için aralığında olması gerekir. 10.000 değerini gama düzeltmesi anlamına gelir.

*caBlueGamma*<br/>
Mavi birincil kaynak renkler n. power gama düzeltmesi değerini belirtir. Değeri 2.500 65,000 için aralığında olması gerekir. 10.000 değerini gama düzeltmesi anlamına gelir.

*caReferenceBlack*<br/>
Kaynak renkler için Siyah başvuru belirtir. Bu değerden daha koyu bir renk siyah olarak kabul edilir. Değeri 4.000-0 aralığında olması gerekir.

*caReferenceWhite*<br/>
Kaynak renkler için Beyaz başvuru belirtir. Bu değerden daha açık olan tüm renkler beyaz olarak kabul edilir. Değer, 10.000-6.000 aralığında olmalıdır.

*caContrast*<br/>
Kaynak nesnesine uygulanacak Karşıtlık miktarını belirtir. Değer, 100 -100 aralığında olmalıdır. 0 değeri, karşıtlık ayarlama yok anlamına gelir.

*caBrightness*<br/>
Kaynak nesnesine uygulanacak parlaklığını belirtir. Değer, 100 -100 aralığında olmalıdır. 0 değeri, parlaklık ayarlama yok anlamına gelir.

*caColorfulness*<br/>
Kaynak nesnesine uygulanacak colorfulness miktarını belirtir. Değer, 100 -100 aralığında olmalıdır. 0 değeri hiçbir colorfulness ayarlama anlamına gelir.

*caRedGreenTint*<br/>
Kaynak nesnesine uygulanacak kırmızı veya yeşil renk tonu ayarlama miktarını belirtir. Değer, 100 -100 aralığında olmalıdır. Pozitif sayı kırmızı ayarlamak ve negatif sayıları yeşil doğru ayarlayın. 0 renk tonu ayarlama yok anlamına gelir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)

