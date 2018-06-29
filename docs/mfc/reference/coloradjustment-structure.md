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
ms.openlocfilehash: 1bb4cba5ef2eafa27a26c945f8754eb1a0ab0315
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37077961"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT Yapısı
`COLORADJUSTMENT` Yapısını tanımlar Windows tarafından kullanılan rengi ayarlama değerleri `StretchBlt` ve `StretchDIBits` işlevleri zaman `StretchBlt` modu **noktalı**.  
  
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
 *caSize*  
 Yapı boyutunu bayt cinsinden belirtir.  
  
 *caFlags*  
 Çıktı görüntü nasıl hazırlıklı olmalıdır belirtir. Bu üye ayarlanabilir **NULL** veya herhangi bir birleşimini aşağıdaki değerlerden biri:  
  
- **CA_NEGATIVE** özgün görüntüsüne negatif görüntülenmelidir belirtir.  
  
- **CA_LOG_FILTER** Logaritmik işlevi çıktı renkleri son yoğunluğu için geçerli olduğunu belirtir. Aydınlatma düşük olduğunda bu renk karşıtlığını artırır.  
  
 *caIlluminantIndex*  
 Resim nesnesi görüntülendiği ışık kaynağının aydınlatma belirtir. Bu üye aşağıdaki değerlerden birine ayarlanabilir:  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 Kaynak renkten kırmızı birincil n. güç gama düzeltmesi değerini belirtir. Değerin 65,000-2.500 aralığında olması gerekir. 10.000 değeri hiçbir gama düzeltmesi anlamına gelir.  
  
 *caGreenGamma*  
 Kaynak renkten yeşil birincil n. güç gama düzeltmesi değerini belirtir. Değerin 65,000-2.500 aralığında olması gerekir. 10.000 değeri hiçbir gama düzeltmesi anlamına gelir.  
  
 *caBlueGamma*  
 Kaynak renkler mavi birincil n. güç gama düzeltmesi değerini belirtir. Değerin 65,000-2.500 aralığında olması gerekir. 10.000 değeri hiçbir gama düzeltmesi anlamına gelir.  
  
 *caReferenceBlack*  
 Kaynak renkler için Siyah başvuru belirtir. Bu değerden daha koyu renkleri siyah olarak kabul edilir. Değer, 0-aralığında 4.000 olmalıdır.  
  
 *caReferenceWhite*  
 Kaynak renkler için Beyaz başvuru belirtir. Bu açık olan tüm renkleri, teknik kabul edilir. Değerin 10.000 6,000 aralığında olması gerekir.  
  
 *caContrast*  
 Kaynak nesneye uygulanan karşıtlık miktarını belirtir. Değer, 100 -100 aralığında olmalıdır. 0 değeri hiçbir karşıtlığını ayarlama anlamına gelir.  
  
 *caBrightness*  
 Kaynak nesneye uygulanacak parlaklığını belirtir. Değer, 100 -100 aralığında olmalıdır. 0 değeri hiçbir parlaklığını ayarlama anlamına gelir.  
  
 *caColorfulness*  
 Kaynak nesneye uygulanacak colorfulness miktarını belirtir. Değer, 100 -100 aralığında olmalıdır. 0 değeri hiçbir colorfulness ayarlama anlamına gelir.  
  
 *caRedGreenTint*  
 Kaynak nesneye uygulanacak kırmızı veya yeşil TINT ayarlama miktarını belirtir. Değer, 100 -100 aralığında olmalıdır. Pozitif sayıları doğru kırmızı ayarlamak ve negatif sayıları doğru yeşil ayarlayın. 0 TINT ayarlama yok anlamına gelir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


