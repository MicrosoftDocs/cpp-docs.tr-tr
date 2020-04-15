---
title: Denetime Sütun Ekleme (Rapor Görünümü)
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
ms.openlocfilehash: 34d7b62985748b9b9d741c083ec9b34fce06b309
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370871"
---
# <a name="adding-columns-to-the-control-report-view"></a>Denetime Sütun Ekleme (Rapor Görünümü)

> [!NOTE]
> Aşağıdaki yordam bir [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md) nesnesi için geçerlidir.

Bir liste denetimi rapor görünümündeolduğunda, sütunlar görüntülenir ve her liste denetim öğesinin çeşitli alt öğelerini düzenleme yöntemi sağlar. Bu kuruluş, liste denetimindeki bir sütun la liste denetim öğesinin ilişkili alt öğesi arasında bire bir yazışma yla uygulanır. Alt öğeler hakkında daha fazla bilgi için [bkz.](../mfc/adding-items-to-the-control.md) Rapor görünümündeki liste denetiminin bir örneği, Windows 95 ve Windows 98 Explorer'daki Ayrıntılar görünümü tarafından sağlanır. İlk sütunklasörü, dosya simgelerini ve etiketleri listeler. Diğer sütunlar liste dosya boyutu, dosya türü, tarih son değiştirilen ve benzeri.

Sütunlar herhangi bir zamanda liste denetimine eklenebilse de, sütunlar `LVS_REPORT` yalnızca denetim stil biti açık olduğunda görünür.

Her sütunda, sütunu etiketlerek ve kullanıcıların sütunu yeniden boyutlandırmasına olanak tanıyan ilişkili bir üstbilgi öğesi (bkz. [CHeaderCtrl)](../mfc/reference/cheaderctrl-class.md)nesnesi vardır.

Liste denetiminiz bir rapor görünümünü destekliyorsa, liste denetim öğesindeki olası her öğe için bir sütun eklemeniz gerekir. [LVCOLUMN](/windows/win32/api/commctrl/ns-commctrl-lvcolumnw) yapısı hazırlayıp [InsertColumn'a](../mfc/reference/clistctrl-class.md#insertcolumn)çağrı yaparak sütun ekleyin. Gerekli sütunları (bazen üstbilgi öğeleri olarak da adlandırılır) ekledikten sonra, bunları katıştırılmış üstbilgi denetimine ait üye işlevleri ve stilleri kullanarak yeniden sıralayabilirsiniz. Daha fazla bilgi için [bkz.](../mfc/ordering-items-in-the-header-control.md)

> [!NOTE]
> Liste denetimi **LVS_NOCOLUMNHEADER** stiliyle oluşturulursa, sütun ekleme girişimi yoksayılır.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
