---
title: (Rapor görünümü) denetime sütun ekleme | Microsoft Docs
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
ms.openlocfilehash: bf967a3a1557bdba8f372c6f277f62eb257befee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392001"
---
# <a name="adding-columns-to-the-control-report-view"></a>Denetime Sütun Ekleme (Rapor Görünümü)

> [!NOTE]
>  Aşağıdaki yordam ya da geçerlidir. bir [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md) nesne.

Liste denetimi rapor görünümü'nde, her liste denetim öğesi çeşitli alt öğelerini düzenleme, bir yöntem sağlayarak sütunlar görüntülenir. Bu kuruluşun bir sütunda bir liste denetimi ve liste denetimi öğesinin ilişkili alt arasında bire bir iletişimin ile birlikte uygulanır. Alt öğeler hakkında daha fazla bilgi için bkz. [denetime öğe ekleme](../mfc/adding-items-to-the-control.md). Liste denetimi rapor görünümü'nde bir örneği, Windows 95 ve Windows 98 Gezgini Ayrıntıları görünümünde tarafından sağlanır. İlk sütun, klasör, dosya simgelerin ve etiketlerin listeler. Dosya boyutu, dosya türü, son değiştirilme tarihi ve benzeri diğer sütunları listeleyin.

Herhangi bir zamanda bu sütun bir liste denetimine eklenebilir olsa da, denetim varsa sütunları görünür `LVS_REPORT` açık stil bit.

Her sütun bir ilişkili üstbilgi öğesi var (bkz [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) sütun etiketleri ve sütunu yeniden boyutlandırmak kullanıcıların sağlayan nesne.

Rapor görünümü, liste denetimini destekliyorsa, her olası alt için bir sütun listesi denetim öğesini eklemeniz gerekir. Hazırlayarak sütun ekleme bir [LV_COLUMN](/windows/desktop/api/commctrl/ns-commctrl-taglvcolumna) yapısı ve ardından bir çağrı yapmadan [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn). (Bazen üstbilgi öğeleri adlandırılır) gerekli sütunları ekledikten sonra bunları sıralayabilirsiniz üye işlevleri ve katıştırılmış üstbilgi denetimine ait stilleri kullanarak. Daha fazla bilgi için [üstbilgi denetimindeki öğeleri sıralama](../mfc/ordering-items-in-the-header-control.md).

> [!NOTE]
>  Liste denetimi ile oluşturulursa **LVS_NOCOLUMNHEADER** stili, sütunları eklemek üzere her türlü girişim yok sayılacak.

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

