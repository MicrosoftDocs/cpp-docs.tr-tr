---
title: LOGBRUSH yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15b904a07eb668a59a269741973424aa30e15877
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336412"
---
# <a name="logbrush-structure"></a>LOGBRUSH Yapısı
`LOGBRUSH` Yapısı, stil, rengini ve fiziksel bir fırça deseni tanımlar. Windows tarafından kullanılan [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) ve [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *lbStyle*  
 Fırça stilini belirtir. `lbStyle` Üye aşağıdaki stilleri biri olmalıdır:  
  
- BS_DIBPATTERN bir desen Fırçası tarafından bir CİHAZDAN bağımsız bit eşlem (DIB) belirtimi tanımlanır. Varsa *lbStyle* BS_DIBPATTERN, olan `lbHatch` üyeyi içeren bir paket DIB işleyici.  
  
- BS_DIBPATTERNPT bir desen Fırçası tarafından bir CİHAZDAN bağımsız bit eşlem (DIB) belirtimi tanımlanır. Varsa *lbStyle* BS_DIBPATTERNPT, olan `lbHatch` üyeyi içeren bir paket DIB işaretçisi.  
  
- Fırça BS_HATCHED çizgili.  
  
- Fırça BS_HOLLOW boş.  
  
- BS_NULL BS_HOLLOW aynıdır.  
  
- Bir bellek bit eşlem tarafından tanımlanan BS_PATTERN Desen fırçası.  
  
- BS_SOLID düz fırça.  
  
 *lbColor*  
 Fırça çizilecek olduğu rengini belirtir. Varsa *lbStyle* BS_HOLLOW veya BS_PATTERN stili *lbColor* göz ardı edilir. Varsa *lbStyle* BS_DIBPATTERN veya BS_DIBPATTERNBT, düşük düzey sözcüğün *lbColor* belirtir olup olmadığını `bmiColors` üyeleri [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) yapısı Açık kırmızı, yeşil, mavi (RGB) değeri veya dizinleri şu anda gerçekleşen mantıksal paletini içerir. `lbColor` Üyesi şu değerlerden biri olmalıdır:  
  
- Renk tablosunu DIB_PAL_COLORS 16-bit dizinlerini dizisi şu anda gerçekleşen mantıksal paletini oluşur.  
  
- Renk tablosunu DIB_RGB_COLORS değişmez değer RGB değerleri içerir.  
  
 *lbHatch*  
 Bir tarama stilini belirtir. Tarafından tanımlanan fırça stili anlamı bağımlı *lbStyle*. Varsa *lbStyle* BS_DIBPATTERN, olan `lbHatch` üyeyi içeren bir paket DIB işleyici. Varsa *lbStyle* BS_DIBPATTERNPT, olan `lbHatch` üyeyi içeren bir paket DIB işaretçisi. Varsa *lbStyle* BS_HATCHED, olan `lbHatch` üye tarama oluşturmak için kullanılan satırları yönünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- Yukarı, soldan sağa HS_BDIAGONAL A 45 derece tarama  
  
- HS_CROSS yatay ve dikey çapraz tarama  
  
- HS_DIAGCROSS 45 derece çapraz tarama  
  
- Aşağıya, soldan sağa HS_FDIAGONAL A 45 derece tarama  
  
- HS_HORIZONTAL yatay tarama  
  
- HS_VERTICAL dikey tarama  
  
 Varsa *lbStyle* BS_PATTERN, olan *lbHatch* deseni tanımlayan bir bit eşlem işleyicisidir. Varsa *lbStyle* BS_SOLID veya BS_HOLLOW, *lbHatch* göz ardı edilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Ancak *lbColor* tarama fırça ön plan rengini denetler [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) ve [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) işlevleri denetim arka plan rengi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

