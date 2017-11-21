---
title: "Cmfcımagepaintarea::ımage_edıt_mode numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IMAGE_EDIT_MODE Enumeration
dev_langs: C++
helpviewer_keywords: IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd59e80dfd019627c0ebe88e116e225f92e3a8ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması
Görüntü Düzenleyicisi iletişim kutusunda bir görüntüsünü değiştirmek için kullandığınız bir çizim modunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum IMAGE_EDIT_MODE  
{  
    IMAGE_EDIT_MODE_PEN = 0,  
    IMAGE_EDIT_MODE_FILL, 
    IMAGE_EDIT_MODE_LINE, 
    IMAGE_EDIT_MODE_RECT, 
    IMAGE_EDIT_MODE_ELLIPSE, 
    IMAGE_EDIT_MODE_COLOR 
};  
```  
  
## <a name="members"></a>Üyeler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`IMAGE_EDIT_MODE_PEN`|Tek tek piksel çizmek için kullanılır.|  
|`IMAGE_EDIT_MODE_FILL`|Geçerli imleç konumu rengi içeren tüm bitişik alanları doldurmak için kullanılır.|  
|`IMAGE_EDIT_MODE_LINE`|Bir çizgi çizmek için kullanılır.|  
|`IMAGE_EDIT_MODE_RECT`|Dikdörtgen çizmek için kullanılır.|  
|`IMAGE_EDIT_MODE_ELLIPSE`|Elips çizmek için kullanılır.|  
|`IMAGE_EDIT_MODE_COLOR`|Geçerli rengi renk geçerli İmleç konumuna ayarlamak için kullanılır.|  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCImagePaintArea` Ve `CMFCImageEditorDialog` sınıflarını geçerli çizim modu ayarlamak için bu numaralandırma kullanın. Çizim modu ve geçerli renk resim alanı bir görüntü Düzenleyici iletişim kutusunda değiştirmek için kullanılır. Hakkında daha fazla bilgi için `CMFCImagePaintArea` ve `CMFCImageEditorDialog`, bkz: [CMFCImagePaintArea sınıfı](../../mfc/reference/cmfcimagepaintarea-class.md) ve [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
 Seçtiğinizde, bir renk görüntüden kullanarak `IMAGE_EDIT_MODE_COLOR` framework geçerli çizim modu ayarlar çizim modu, `IMAGE_EDIT_MODE_PEN`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afximagepaintarea.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea sınıfı](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
