---
title: (Rapor görünümü) denetimine sütunlar ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 975d65119ba0ae24b236d96cbe67e73b70be6bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341835"
---
# <a name="adding-columns-to-the-control-report-view"></a>Denetime Sütun Ekleme (Rapor Görünümü)
> [!NOTE]
>  Aşağıdaki yordam için geçerli bir [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md) nesnesi.  
  
 Liste denetimi rapor görünümünde olduğunda, her liste denetim öğesi çeşitli alt öğelerini düzenleme bir yöntem sağlama sütunlar görüntülenir. Bu kuruluş bire bir sütunda liste denetimi ve liste denetimi öğesinin ilişkili alt arasında ile uygulanır. Alt öğeler hakkında daha fazla bilgi için bkz: [denetime öğe eklemeyi](../mfc/adding-items-to-the-control.md). Rapor görünümünde liste denetimi örneği, Windows 95 ve Windows 98 Gezgini Ayrıntıları görünümünde tarafından sağlanır. İlk sütun, klasör, dosya simgelerinde ve etiketleri listeler. Dosya boyutu, dosya türü, son değiştirilme tarihi ve benzeri diğer sütunları listeleyin.  
  
 Herhangi bir zamanda bir liste denetimine sütunlar eklenebilir olsa bile, yalnızca denetimi olduğunda sütunları görünür `LVS_REPORT` açık stili bit.  
  
 Her sütunun bir ilişkili üstbilgi öğesi vardır (bkz [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) sütun etiketleri ve sütunu yeniden boyutlandırmak kullanıcıların sağlayan nesne.  
  
 Liste denetimi rapor görünümü destekliyorsa, bir liste denetim öğesi bir sütun için olası her alt eklemeniz gerekir. Hazırlama tarafından bir sütun ekleyin bir [LV_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) yapısı ve ardından bir çağrı yaparak [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn). (Bazen üstbilgi öğeleri adlandırılır) gerekli sütunların eklendikten sonra bunları sıralayabilirsiniz üye işlevleri ve katıştırılmış üstbilgi denetimine ait stilleri kullanarak. Daha fazla bilgi için bkz: [üstbilgi denetimindeki öğeleri sıralama](../mfc/ordering-items-in-the-header-control.md).  
  
> [!NOTE]
>  Liste denetimi ile oluşturulursa **LVS_NOCOLUMNHEADER** stili, sütun eklemek için her türlü girişim yok sayılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

