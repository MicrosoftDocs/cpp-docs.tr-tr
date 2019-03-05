---
title: Denetim Çubuğu Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: 3426d84eab888a6fe78b663945776fff2fe708dd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302253"
---
# <a name="control-bar-classes"></a>Denetim Çubuğu Sınıfları

Denetim çubukları çerçeve penceresine eklenir. Düğmeler, durum bölmeleri veya bir iletişim şablonunu içerirler. Takılı denetim çubukları, araç paletleri olarak da bilinir, ekleyerek uygulandığından bir [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) nesne.

## <a name="framework-control-bars"></a>Framework denetim çubukları

Bu denetim çubukları MFC çerçevesi ayrılmaz bir parçasıdır. Bunlar, kullanmayı daha kolay ve framework ile tümleşik olduğu için Windows çubukları denetlemek çok daha güçlü. Çoğu MFC uygulamaları, Windows Denetim çubukları yerine bu denetim çubuklarını kullanın.

[CControlBar](../mfc/reference/ccontrolbar-class.md)<br/>
Bu bölümde listelenen MFC denetim çubukları için temel sınıf. Denetim çubuğu, bir çerçeve penceresi kenarına hizalanır bir penceredir. Denetim çubuğu ya da içeren `HWND`-alt veya denetimleri göre değil temel bir `HWND`, araç çubuğu düğmeleri gibi.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
Bir iletişim kutusu şablonu temel alan bir denetim çubuğu.

[CReBar](../mfc/reference/crebar-class.md)<br/>
Ek alt pencereleri biçiminde denetimleri içerebilen bir araç çubuğu destekler.

[CToolBar](../mfc/reference/ctoolbar-class.md)<br/>
Bit eşlem komut düğmeleri içermemesi araç çubuğu denetimi windows temel alan bir `HWND`. Bu sınıf MFC uygulamaları çoğu kullanmak yerine `CToolBarCtrl`.

[CStatusBar](../mfc/reference/cstatusbar-class.md)<br/>
Durum çubuğu denetimi windows için temel sınıf. Bu sınıf MFC uygulamaları çoğu kullanmak yerine `CStatusBarCtrl`.

## <a name="windows-control-bars"></a>Windows Denetim çubukları

Bu denetim çubukları karşılık gelen Windows denetimleri için ince sarmalayıcıları ' dir. Framework ile tümleşik değil çünkü bunlar daha zor daha önce listelenen denetim çubukları kullanmak üzeresiniz. Çoğu MFC uygulamaları, daha önce listelenen denetim çubuklarını kullanın.

[CRebarCtrl](../mfc/reference/crebarctrl-class.md)<br/>
İç denetim uygulayan `CRebar` nesne.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Yatay bir pencere genellikle uygulama durum bilgilerini görüntüleyebilen bölmelere bölünür.

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Windows ortak araç çubuğu denetimi işlevlerini sağlar.

## <a name="related-classes"></a>İlgili sınıflar

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Bir uygulamada bir aracın amacını açıklayan metnin tek bir çizgi görüntüler küçük bir açılır pencere.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
Kalıcı depolama, yerleştirme denetim çubukları için eyalet verilerini işler.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
