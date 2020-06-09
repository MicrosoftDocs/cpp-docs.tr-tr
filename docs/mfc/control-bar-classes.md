---
title: Denetim Çubuğu Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: f89770683edb1f4268b4f19adb74e5c08aa5f109
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620520"
---
# <a name="control-bar-classes"></a>Denetim Çubuğu Sınıfları

Denetim çubukları bir çerçeve penceresine eklenir. Düğmeler, durum bölmeleri veya bir iletişim kutusu şablonu içerirler. Araç paletleri olarak da bilinen serbest kayan denetim çubukları, bunları bir [CMiniFrameWnd](reference/cminiframewnd-class.md) nesnesine ekleyerek uygulanır.

## <a name="framework-control-bars"></a>Çerçeve denetim çubukları

Bu denetim çubukları MFC çerçevesinin ayrılmaz bir parçasıdır. Bunlar, çerçevesiyle tümleştirildiği için Windows Denetim çubuklarıyla daha kolay ve daha güçlü bir şekilde kullanılır. Çoğu MFC uygulaması, Windows Denetim çubukları yerine bu denetim çubuklarını kullanır.

[CControlBar](reference/ccontrolbar-class.md)<br/>
Bu bölümde listelenen MFC denetim çubuklarının temel sınıfı. Bir denetim çubuğu, bir çerçeve penceresinin kenarına hizalanmış bir penceredir. Denetim çubuğu `HWND` , bir veya bir `HWND` araç çubuğu düğmesi gibi tabanlı alt denetimler veya denetimler içerir.

[CDialogBar](reference/cdialogbar-class.md)<br/>
İletişim kutusu şablonunu temel alan bir denetim çubuğu.

[CReBar](reference/crebar-class.md)<br/>
, Denetim biçiminde ek alt pencereler içerebilen bir araç çubuğunu destekler.

[CToolBar](reference/ctoolbar-class.md)<br/>
' A dayalı olmayan bit eşlem komut düğmelerini içeren araç çubuğu denetimi pencereleri `HWND` . Çoğu MFC uygulaması yerine bu sınıfı kullanır `CToolBarCtrl` .

[CStatusBar](reference/cstatusbar-class.md)<br/>
Durum çubuğu denetim pencereleri için temel sınıf. Çoğu MFC uygulaması yerine bu sınıfı kullanır `CStatusBarCtrl` .

## <a name="windows-control-bars"></a>Windows Denetim çubukları

Bu denetim çubukları, ilgili Windows denetimleri için ince sarmalayıcılardır. Framework ile tümleştirildiği için, daha önce listelenmiş olan denetim çubuklarıyla kullanmaktan daha zordur. Çoğu MFC uygulaması daha önce listelenen denetim çubuklarını kullanır.

[CRebarCtrl](reference/crebarctrl-class.md)<br/>
Nesnenin iç denetimini uygular `CRebar` .

[CStatusBarCtrl](reference/cstatusbarctrl-class.md)<br/>
Bir uygulamanın durum bilgilerini görüntüleyebilen, genellikle bölmelere ayrılmış yatay bir pencere.

[CToolBarCtrl](reference/ctoolbarctrl-class.md)<br/>
Windows Toolbar ortak denetiminin işlevlerini sağlar.

## <a name="related-classes"></a>İlgili sınıflar

[CToolTipCtrl](reference/ctooltipctrl-class.md)<br/>
Uygulamadaki bir aracın amacını açıklayan tek satırlık bir metin görüntüleyen küçük bir açılır pencere.

[CDockState](reference/cdockstate-class.md)<br/>
Denetim çubukları için yerleştirme durumu verilerinin kalıcı depolamayı işler.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
