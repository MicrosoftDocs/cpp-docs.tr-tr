---
title: Denetim Çubuğu Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: a050c5d2f7396324c2c380a03fc28e01ab992208
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440955"
---
# <a name="control-bar-classes"></a>Denetim Çubuğu Sınıfları

Denetim çubukları bir çerçeve penceresine eklenir. Düğmeler, durum bölmeleri veya bir iletişim kutusu şablonu içerirler. Araç paletleri olarak da bilinen serbest kayan denetim çubukları, bunları bir [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) nesnesine ekleyerek uygulanır.

## <a name="framework-control-bars"></a>Çerçeve denetim çubukları

Bu denetim çubukları MFC çerçevesinin ayrılmaz bir parçasıdır. Bunlar, çerçevesiyle tümleştirildiği için Windows Denetim çubuklarıyla daha kolay ve daha güçlü bir şekilde kullanılır. Çoğu MFC uygulaması, Windows Denetim çubukları yerine bu denetim çubuklarını kullanır.

[CControlBar](../mfc/reference/ccontrolbar-class.md)<br/>
Bu bölümde listelenen MFC denetim çubuklarının temel sınıfı. Bir denetim çubuğu, bir çerçeve penceresinin kenarına hizalanmış bir penceredir. Denetim çubuğu, araç çubuğu düğmeleri gibi `HWND`tabanlı olmayan `HWND`tabanlı alt denetimleri ya da denetimleri içerir.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
İletişim kutusu şablonunu temel alan bir denetim çubuğu.

[CReBar](../mfc/reference/crebar-class.md)<br/>
, Denetim biçiminde ek alt pencereler içerebilen bir araç çubuğunu destekler.

[CToolBar](../mfc/reference/ctoolbar-class.md)<br/>
Bir `HWND`tabanlı olmayan bit eşlem komut düğmelerini içeren araç çubuğu denetimi pencereleri. Çoğu MFC uygulaması `CToolBarCtrl`yerine bu sınıfı kullanır.

[CStatusBar](../mfc/reference/cstatusbar-class.md)<br/>
Durum çubuğu denetim pencereleri için temel sınıf. Çoğu MFC uygulaması `CStatusBarCtrl`yerine bu sınıfı kullanır.

## <a name="windows-control-bars"></a>Windows Denetim çubukları

Bu denetim çubukları, ilgili Windows denetimleri için ince sarmalayıcılardır. Framework ile tümleştirildiği için, daha önce listelenmiş olan denetim çubuklarıyla kullanmaktan daha zordur. Çoğu MFC uygulaması daha önce listelenen denetim çubuklarını kullanır.

[CRebarCtrl](../mfc/reference/crebarctrl-class.md)<br/>
`CRebar` nesnesinin iç denetimini uygular.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Bir uygulamanın durum bilgilerini görüntüleyebilen, genellikle bölmelere ayrılmış yatay bir pencere.

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Windows Toolbar ortak denetiminin işlevlerini sağlar.

## <a name="related-classes"></a>İlgili sınıflar

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Uygulamadaki bir aracın amacını açıklayan tek satırlık bir metin görüntüleyen küçük bir açılır pencere.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
Denetim çubukları için yerleştirme durumu verilerinin kalıcı depolamayı işler.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
