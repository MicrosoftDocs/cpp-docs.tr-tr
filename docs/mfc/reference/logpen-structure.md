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
ms.openlocfilehash: 4c0e07ce3a38eaca54e860ebe821924c0f564c69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374156"
---
# <a name="logpen-structure"></a>LOGPEN Yapısı
`LOGPEN` Yapısı stili, genişlik ve bir kalemin rengini tanımlar, satırları ve Kenarlıkları çizmek için kullanılan bir çizim nesnesi. [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) işlev kullandığı `LOGPEN` yapısı.  
  
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
 Kalem türünü belirtir. Bu üye aşağıdaki değerlerden biri olabilir:  
  
- **PS_SOLID** düz kalem oluşturur.  
  
- **PS_DASH** kesikli kalem oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- **PS_DOT** noktalı kalem oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- **PS_DASHDOT** değişen kısa çizgi ve nokta ile kalem oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- **PS_DASHDOTDOT** değişen kısa çizgi ve çift nokta kalem oluşturur. (Yalnızca kalem genişliği 1 olduğunda geçerlidir.)  
  
- **PS_NULL** null kalem oluşturur.  
  
- **PS_INSIDEFRAME** sınırlayıcı dikdörtgenini belirtin GDI çıkış işlevleri tarafından üretilen kapalı şekiller çerçeve içine bir satır çizer kalem oluşturur (örneğin, **elips**, **dikdörtgen**, `RoundRect`, `Pie`, ve `Chord` üye işlevleri). Bu stili GDI ile kullanıldığında çıktı sınırlayıcı dikdörtgenini belirtmeyin işlevleri (örneğin, `LineTo` üye işlevi), kalem çizim alanının çerçevesi tarafından sınırlı değildir.  
  
     Kalem varsa **PS_INSIDEFRAME** stili ve bir renk mantıksal renk tablosundaki eşleşmeyen bir renk kalem Titremeli renk ile çizilir. **PS_SOLID** kalem stilini kalem Titremeli renk ile oluşturmak için kullanılamaz. **PS_INSIDEFRAME** stili aynıdır **PS_SOLID** kalem genişliği 1 küçük veya buna eşit olması durumunda.  
  
     Zaman **PS_INSIDEFRAME** stili dışındaki işlevler tarafından üretilen GDI nesneleri ile kullanılan **elips**, **dikdörtgen**, ve `RoundRect`, satır tamamen olmayabilir Belirtilen çerçeve içine.  
  
 *lopnWidth*  
 Kalem genişliği mantıksal birimler cinsinden belirtir. Varsa **lopnWidth** üye 0, 1 piksel genişliğinde geçerli eşleme modu bakılmaksızın ızgara cihazlarda kalem değil.  
  
 *lopnColor*  
 Kalem rengini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 **y** değeri [noktası](../../mfc/reference/point-structure1.md) için yapı **lopnWidth** üye kullanılmıyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

