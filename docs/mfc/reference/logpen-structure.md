---
title: LOGPEN yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c677f86a44d24e0d0d2742d47ee1534532001528
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338538"
---
# <a name="logpen-structure"></a>LOGPEN Yapısı
`LOGPEN` Yapısı, stil, genişliğini ve bir kalemin rengini tanımlar, çizmek için kullanılan Titizlik satırları ve kenarlıklar. [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) işlevini kullanan `LOGPEN` yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *lopnStyle*  
 Kalem türünü belirtir. Bu üye, aşağıdaki değerlerden biri olabilir:  
  
- Düz kalem PS_SOLID oluşturur.  
  
- PS_DASH kesikli kalem oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- PS_DOT noktalı kalem oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- Kalem değişen ile çizgi ve nokta PS_DASHDOT oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- PS_DASHDOTDOT kalem ile çizgi ve çift nokta değişen bir oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- PS_NULL null kalem oluşturur.  
  
- PS_INSIDEFRAME GDI oluşturduğu kapalı şekiller çerçevenin içine bir çizgi çizer bir kalem üretilen çıkış sınırlayıcı bir dikdörtgen belirtin işlevleri (örneğin, `Ellipse`, `Rectangle`, `RoundRect`, `Pie`, ve `Chord` üyesi İşlevler). Bu stil GDI ile kullanıldığında çıktı sınırlayıcı bir dikdörtgen belirtmeyin işlevleri (örneğin, `LineTo` üye işlevi), çerçeve tarafından kalemi çizim alanının sınırlı değildir.  
  
     Kalem PS_INSIDEFRAME stili ve mantıksal bir renk tablosundaki bir renk eşleşmeyen bir renk varsa, kalem bir Titremeli renk ile çizilir. PS_SOLID kalem stili bir Titremeli renk ile bir kalem oluşturmak için kullanılamaz. Kalem genişliği 1'e eşit veya küçükse PS_INSIDEFRAME stili PS_SOLID için aynıdır.  
  
     GDI nesneleri ile PS_INSIDEFRAME stili kullanıldığında üretilen işlevleri tarafından dışında `Ellipse`, `Rectangle`, ve `RoundRect`, satır içinde belirtilen çerçeve tamamen olmayabilir.  
  
 *lopnWidth*  
 Kalem genişliği mantıksal birimler cinsinden belirtir. Varsa `lopnWidth` üye 0, 1 piksel genişliğinde geçerli eşleme modunu bakılmaksızın ızgara cihazlarda kalem değil.  
  
 *lopnColor*  
 Kalem rengi belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 `y` Değerini [noktası](../../mfc/reference/point-structure1.md) için yapı `lopnWidth` üye kullanılmaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

