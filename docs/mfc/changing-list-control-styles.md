---
description: 'Daha fazla bilgi edinin: liste denetim stillerini değiştirme'
title: Liste Denetim Stillerini Değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: a6712baf5ea1e161ec1fd73e25ea01fedd650670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339741"
---
# <a name="changing-list-control-styles"></a>Liste Denetim Stillerini Değiştirme

Bir liste denetiminin pencere stilini ([CListCtrl](reference/clistctrl-class.md)) oluşturduktan sonra istediğiniz zaman değiştirebilirsiniz. Pencere stilini değiştirerek, denetimin kullandığı görünüm türünü değiştirirsiniz. Örneğin, Gezgin 'e öykünmek için, farklı görünümler arasında denetimi değiştirmek için menü öğeleri veya araç çubuğu düğmeleri sağlayabilirsiniz: simge görünümü, liste görünümü vb.

Örneğin, Kullanıcı menü öğesini seçtiğinde, denetimin geçerli stilini almak için [GetWindowLong](/windows/win32/api/winuser/nf-winuser-getwindowlongw) öğesine çağrı yapıp stili sıfırlamak Için [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) çağrısı yapabilirsiniz. Daha fazla bilgi için, bkz. Windows SDK [liste görünümü denetimlerini kullanma](/windows/win32/Controls/using-list-view-controls) .

Kullanılabilir stiller [oluşturma](reference/clistctrl-class.md#create)bölümünde listelenmiştir. Stiller **LVS_ICON**, **LVS_SMALLICON**, **LVS_LIST** ve **LVS_REPORT** dört liste denetim görünümünü belirleyebilirler.

## <a name="extended-styles"></a>Genişletilmiş stiller

Bir liste denetimi için standart stillere ek olarak, genişletilmiş stiller olarak adlandırılan başka bir küme vardır. Windows SDK [Genişletilmiş liste görünümü stillerinde](/windows/win32/Controls/extended-list-view-styles) açıklanan bu stiller, liste denetiminizin davranışını özelleştiren çeşitli yararlı özellikler sağlar. Belirli bir stilin (örneğin, vurgulu seçim) davranışını uygulamak için, [Clienstctrl:: Seestdedstyle](reference/clistctrl-class.md#setextendedstyle)öğesine bir çağrı yapıp gerekli stili geçirerek. Aşağıdaki örnek işlev çağrısını gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#22](codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> Üzerine gelme seçiminin çalışması için **LVS_EX_ONECLICKACTIVATE** ya da **LVS_EX_TWOCLICKACTIVATE** açık olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
