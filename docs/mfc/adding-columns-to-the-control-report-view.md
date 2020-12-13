---
description: 'Hakkında daha fazla bilgi edinin: denetime sütun ekleme (rapor görünümü)'
title: Denetime Sütun Ekleme (Rapor Görünümü)
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
ms.openlocfilehash: 62e874f77d326b80a362791888e75df0a92781d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339102"
---
# <a name="adding-columns-to-the-control-report-view"></a>Denetime Sütun Ekleme (Rapor Görünümü)

> [!NOTE]
> Aşağıdaki yordam, bir [CListView](reference/clistview-class.md) veya [CListCtrl](reference/clistctrl-class.md) nesnesi için geçerlidir.

Liste denetimi rapor görünümünde olduğunda, her liste denetim öğesinin çeşitli alt öğelerini düzenleme yöntemi sağlayan sütunlar görüntülenir. Bu kuruluş, liste denetimindeki bir sütun ve liste denetim öğesinin ilişkili alt öğesi arasında bire bir yazışmalar ile uygulanır. Alt öğeler hakkında daha fazla bilgi için bkz. [denetime öğe ekleme](adding-items-to-the-control.md). Rapor görünümündeki liste denetimine bir örnek, Windows 95 ve Windows 98 Explorer 'daki Ayrıntılar görünümü tarafından sağlanmaktadır. İlk sütunda klasör, dosya simgeleri ve Etiketler listelenir. Diğer sütunlarda dosya boyutu, dosya türü, son değiştirilme tarihi vb. listelenmiştir.

Sütunlar bir liste denetimine herhangi bir zamanda eklenebilse de, sütunlar yalnızca denetimin `LVS_REPORT` Stil biti açık olduğunda görünür olur.

Her sütunda, sütunu etiketleyen ve kullanıcıların sütunu yeniden boyutlandırmasına izin veren ilişkili bir üst bilgi öğesi (bkz. [CHeaderCtrl](reference/cheaderctrl-class.md)) nesnesi vardır.

Liste denetiminiz bir rapor görünümünü destekliyorsa, bir liste denetim öğesinde olası her alt öğe için bir sütun eklemeniz gerekir. [Lvcolumn](/windows/win32/api/commctrl/ns-commctrl-lvcolumnw) yapısını hazırlarken ve sonra [InsertColumn](reference/clistctrl-class.md#insertcolumn)çağrısı yaparak bir sütun ekleyin. Gerekli sütunları ekledikten sonra (bazen başlık öğeleri olarak adlandırılır), katıştırılmış üst bilgi denetimine ait üye işlevleri ve stilleri kullanarak bunları yeniden düzenleyebilirsiniz. Daha fazla bilgi için bkz. [üstbilgi denetimindeki öğeleri sıralama](ordering-items-in-the-header-control.md).

> [!NOTE]
> Liste denetimi **LVS_NOCOLUMNHEADER** stille oluşturulduysa, sütun ekleme girişimleri yok sayılır.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
