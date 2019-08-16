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
ms.openlocfilehash: 9321a582f223269ee998dccd01721f47d90eb7fe
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509335"
---
# <a name="adding-columns-to-the-control-report-view"></a>Denetime Sütun Ekleme (Rapor Görünümü)

> [!NOTE]
>  Aşağıdaki yordam, bir [CListView](../mfc/reference/clistview-class.md) veya [CListCtrl](../mfc/reference/clistctrl-class.md) nesnesi için geçerlidir.

Liste denetimi rapor görünümünde olduğunda, her liste denetim öğesinin çeşitli alt öğelerini düzenleme yöntemi sağlayan sütunlar görüntülenir. Bu kuruluş, liste denetimindeki bir sütun ve liste denetim öğesinin ilişkili alt öğesi arasında bire bir yazışmalar ile uygulanır. Alt öğeler hakkında daha fazla bilgi için bkz. [denetime öğe ekleme](../mfc/adding-items-to-the-control.md). Rapor görünümündeki liste denetimine bir örnek, Windows 95 ve Windows 98 Explorer 'daki Ayrıntılar görünümü tarafından sağlanmaktadır. İlk sütunda klasör, dosya simgeleri ve Etiketler listelenir. Diğer sütunlarda dosya boyutu, dosya türü, son değiştirilme tarihi vb. listelenmiştir.

Sütunlar bir liste denetimine herhangi bir zamanda eklenebilse de, sütunlar yalnızca denetimin `LVS_REPORT` stil biti açık olduğunda görünür olur.

Her sütunda, sütunu etiketleyen ve kullanıcıların sütunu yeniden boyutlandırmasına izin veren ilişkili bir üst bilgi öğesi (bkz. [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) nesnesi vardır.

Liste denetiminiz bir rapor görünümünü destekliyorsa, bir liste denetim öğesinde olası her alt öğe için bir sütun eklemeniz gerekir. [Lvcolumn](/windows/win32/api/commctrl/ns-commctrl-lvcolumnw) yapısını hazırlarken ve sonra [InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn)çağrısı yaparak bir sütun ekleyin. Gerekli sütunları ekledikten sonra (bazen başlık öğeleri olarak adlandırılır), katıştırılmış üst bilgi denetimine ait üye işlevleri ve stilleri kullanarak bunları yeniden düzenleyebilirsiniz. Daha fazla bilgi için bkz. [üstbilgi denetimindeki öğeleri sıralama](../mfc/ordering-items-in-the-header-control.md).

> [!NOTE]
>  Liste denetimi **LVS_NOCOLUMNHEADER** stiliyle oluşturulduysa, sütun ekleme girişimleri yok sayılır.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
