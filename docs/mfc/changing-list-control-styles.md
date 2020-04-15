---
title: Liste Denetim Stillerini Değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 5f45e0549c3fc0f5747f8dd12a6310fafd7dd7bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370810"
---
# <a name="changing-list-control-styles"></a>Liste Denetim Stillerini Değiştirme

Bir liste denetiminin pencere stilini[(CListCtrl)](../mfc/reference/clistctrl-class.md)oluşturduktan sonra istediğiniz zaman değiştirebilirsiniz. Pencere stilini değiştirerek, denetimin kullandığı görünüm türünü değiştirirsiniz. Örneğin, Explorer'ı taklit etmek için, denetimi farklı görünümler arasında değiştirmek için menü öğeleri veya araç çubuğu düğmeleri sağlayabilirsiniz: simge görünümü, liste görünümü ve benzeri.

Örneğin, kullanıcı menü öğenizi seçtiğinde, denetimin geçerli stilini almak için [GetWindowLong'a](/windows/win32/api/winuser/nf-winuser-getwindowlongw) çağrı yapabilir ve stili sıfırlamak için [SetWindowLong'u](/windows/win32/api/winuser/nf-winuser-setwindowlongw) arayabilirsiniz. Daha fazla bilgi için Windows SDK'daki [Liste Görünümü Denetimlerini Kullanma'ya](/windows/win32/Controls/using-list-view-controls) bakın.

Kullanılabilir stiller [Oluştur'da](../mfc/reference/clistctrl-class.md#create)listelenir. Stilleri **LVS_ICON**, **LVS_SMALLICON**, **LVS_LIST**, ve **LVS_REPORT** dört liste denetim görünümleri belirlemek.

## <a name="extended-styles"></a>Genişletilmiş Stiller

Liste denetimi için standart stiller ek olarak, genişletilmiş stilleri olarak adlandırılan başka bir küme vardır. Windows SDK'da [Genişletilmiş Liste Görünümü Stilleri'nde](/windows/win32/Controls/extended-list-view-styles) tartışılan bu stiller, liste denetiminizin davranışını özelleştiren çeşitli yararlı özellikler sağlar. Belirli bir stilin davranışını (havada gezinme seçimi gibi) uygulamak için, Gerekli stili geçen [CListCtrl::SetExtendedStyle'ı](../mfc/reference/clistctrl-class.md#setextendedstyle)arayın. Aşağıdaki örnek, işlev çağrısını gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> Gezinme seçiminin işe yaraması **için, LVS_EX_ONECLICKACTIVATE** veya **LVS_EX_TWOCLICKACTIVATE** açık olması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
