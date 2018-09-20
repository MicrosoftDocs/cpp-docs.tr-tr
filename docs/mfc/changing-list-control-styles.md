---
title: Liste Denetim stillerini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfe08e9e1be0c7473cdf9a5ca040730423006906
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427062"
---
# <a name="changing-list-control-styles"></a>Liste Denetim Stillerini Değiştirme

Liste denetimi penceresi stilini değiştirebileceğinize ([CListCtrl](../mfc/reference/clistctrl-class.md)) oluşturduktan sonra dilediğiniz zaman. Styl okna değiştirerek denetimi kullanan bir görünüm türünü değiştirin. Örneğin, Gezgin benzetmek için menü öğesi ya da araç çubuğu düğmeleri, denetimleri farklı görünümler arasında geçiş için sağladığınız: simge görünümünde, liste görünümü ve benzeri.

Örneğin, çağrı yapmak kullanıcı, menü öğesi seçtiğinde [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) geçerli bir denetimin stilini alır ve ardından çağırmak için [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) stili sıfırlanır. Daha fazla bilgi için [liste görünümü denetimi kullanarak](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Kullanılabilir stiller içinde listelenen [Oluştur](../mfc/reference/clistctrl-class.md#create). Stilleri **LVS_ICON**, **komutu etkinleştir**, **LVS_LIST**, ve **LVS_REPORT** dört liste denetimi görünümleri belirleyin.

## <a name="extended-styles"></a>Genişletilmiş stiller

Bir list denetimi için standart stilleri yanı sıra başka bir kümesi, Genişletilmiş Stil olarak başvurulan yoktur. Makalesinde ele alındığı bu stiller, [Genişletilmiş liste görünümü stillerini](/windows/desktop/Controls/extended-list-view-styles) Windows SDK'da çeşitli listesi davranışını özelleştiren yararlı özellikleri sağlar. Davranışı (gelindiğinde seçimi gibi) belirli bir stil uygulamak için çağrı yapmak [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), gerekli stil geçirme. Aşağıdaki örnek, işlev çağrısı göstermektedir:

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
>  Üzerine gelindiğinde kullanılacak seçim çalışmak de sahip olmanız gerekir **LVS_EX_ONECLICKACTIVATE** veya **LVS_EX_TWOCLICKACTIVATE** açık.

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

