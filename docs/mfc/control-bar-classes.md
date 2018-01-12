---
title: "Denetim çubuğu sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.control
dev_langs: C++
helpviewer_keywords: control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44fcecbf1d7ddb6c46469f25349d972c8b317809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="control-bar-classes"></a>Denetim Çubuğu Sınıfları
Denetim çubukları bir çerçeve penceresinde eklenir. Düğmeler, durum bölmeleri veya bir iletişim şablonunu içerir. Aracı paletleri olarak da bilinir serbest kaydırılan denetim çubukları ekleyerek bunları uygulanır bir [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) nesnesi.  
  
## <a name="framework-control-bars"></a>Çerçeve denetim çubukları  
 Bu denetim çubukları MFC çerçevesi ayrılmaz bir parçasıdır. Bunlar kullanmayı daha kolay ve framework ile tümleşik olduğu için Windows çubukları denetimi daha güçlü. MFC uygulamaların çoğu Windows Denetim çubukları yerine bu denetim çubukları kullanın.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 Bu bölümde listelenen MFC denetim çubukları için temel sınıf. Denetim çubuğu bir çerçeve penceresinde kenarına hizalanan bir penceredir. Denetim çubuğu ya da içeren `HWND`-tabanlı veya alt denetimleri göre değil bir `HWND`, araç çubuğu düğmeleri gibi.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 Bir iletişim kutusu şablona dayalı bir denetim çubuğu.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 Ek alt windows denetimleri biçiminde içeren bir araç çubuğu destekler.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 Bit eşlem komut düğmeleri içermemesi araç çubuğu denetimi windows tabanlı bir `HWND`. Bu sınıf MFC uygulamaların çoğu kullanmak yerine `CToolBarCtrl`.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 Durum çubuğu denetim windows için temel sınıf. Bu sınıf MFC uygulamaların çoğu kullanmak yerine `CStatusBarCtrl`.  
  
## <a name="windows-control-bars"></a>Windows Denetim çubukları  
 Bu denetim çubukları karşılık gelen Windows denetimleri için ince sarmalayıcıları ' dir. Framework ile tümleşik değil çünkü bunlar daha önceden listelenen denetim çubukları kullanmak üzeresiniz. Çoğu MFC uygulamaları daha önce listelenen denetim çubuklarını kullanın.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 İç denetimi uygulayan `CRebar` nesnesi.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Genellikle bir uygulama durum bilgilerini görüntüleyebilen bölmeye ayrılmış bir yatay penceresi.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows ortak araç çubuğu denetimi işlevselliğini sağlar.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Tek satırlık bir uygulamada bir aracı amacını açıklayan metin görüntüler küçük bir açılır pencere.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Denetim çubukları durumu verilerini yerleştirme kalıcı depolama işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

