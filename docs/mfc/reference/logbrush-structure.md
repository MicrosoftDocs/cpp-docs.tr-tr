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
ms.openlocfilehash: 6e02c156619e4ca36d268870c70ba783c41a352d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="logbrush-structure"></a>LOGBRUSH Yapısı
`LOGBRUSH` Stili, renk ve fiziksel fırça desenini yapısını tanımlar. Windows tarafından kullanılan [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) ve [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lbStyle`  
 Fırça stilini belirtir. `lbStyle` Üye aşağıdaki stiller biri olmalıdır:  
  
- **BS_DIBPATTERN** bir CİHAZDAN bağımsız bit eşlem (DIB) belirtim tarafından tanımlanan bir desen Fırçası. Varsa `lbStyle` olan **BS_DIBPATTERN**, **lbHatch** üyeyi içeren bir paket DIB için tanıtıcı.  
  
- **BS_DIBPATTERNPT** bir CİHAZDAN bağımsız bit eşlem (DIB) belirtim tarafından tanımlanan bir desen Fırçası. Varsa `lbStyle` olan **BS_DIBPATTERNPT**, **lbHatch** üye paketlenmiş DIB gösteren bir işaretçi içeriyor.  
  
- **BS_HATCHED** fırça çizgili.  
  
- **BS_HOLLOW** fırça içi boş.  
  
- **BS_NULL** aynı **BS_HOLLOW**.  
  
- **BS_PATTERN** bellek bit eşlem tarafından tanımlanan fırça desen.  
  
- **BS_SOLID** düz fırça.  
  
 `lbColor`  
 Fırça çizilecek olduğu rengini belirtir. Varsa `lbStyle` olan **BS_HOLLOW** veya **BS_PATTERN** stili **lbColor** göz ardı edilir. Varsa `lbStyle` olan **BS_DIBPATTERN** veya **BS_DIBPATTERNBT**, düşük düzey sözcüğün **lbColor** belirtir olup olmadığını **bmiColors**üyeleri [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) yapısı, şu anda gerçekleşen mantıksal palet açık kırmızı, yeşil, mavi (RGB) değerleri veya dizinleri içerir. **LbColor** üye aşağıdaki değerlerden biri olmalıdır:  
  
- **DIB_PAL_COLORS** renk tablosu 16 bit dizinlerini dizisi şu anda gerçekleşen mantıksal palet oluşur.  
  
- **DIB_RGB_COLORS** renk tablosu değişmez değer RGB değerleri içerir.  
  
 *lbHatch*  
 Bir tarama stilini belirtir. Tarafından tanımlanan fırça stili anlamı bağlıdır `lbStyle`. Varsa `lbStyle` olan **BS_DIBPATTERN**, **lbHatch** üyeyi içeren bir paket DIB için tanıtıcı. Varsa `lbStyle` olan **BS_DIBPATTERNPT**, **lbHatch** üye paketlenmiş DIB gösteren bir işaretçi içeriyor. Varsa `lbStyle` olan **BS_HATCHED**, **lbHatch** üye tarama oluşturmak için kullanılan satırları yönünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- `HS_BDIAGONAL` 45 derece yukarı, soldan sağa tarama  
  
- `HS_CROSS` Yatay ve dikey bir çapraz tarama  
  
- `HS_DIAGCROSS` 45 derecelik çapraz tarama  
  
- `HS_FDIAGONAL` 45 derecelik aşağı, soldan sağa tarama  
  
- `HS_HORIZONTAL` Yatay tarama  
  
- `HS_VERTICAL` Dikey tarama  
  
 Varsa `lbStyle` olan **BS_PATTERN**, **lbHatch** deseni tanımlayan bit eşlem işleyicisidir. Varsa `lbStyle` olan **BS_SOLID** veya **BS_HOLLOW**, **lbHatch** göz ardı edilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Ancak **lbColor** bir tarama fırça ön plan rengini denetimleri [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) ve [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) işlevleri denetim arka plan rengi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** wingdi.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

