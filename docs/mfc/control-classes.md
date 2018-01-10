---
title: "Denetim sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.control
dev_langs: C++
helpviewer_keywords:
- static display controls [MFC]
- control classes [MFC]
- buttons, MFC control classes
- controls [MFC], MFC control classes
- controls [MFC]
- list boxes [MFC], MFC control classes
- control classes [MFC], MFC
- text, controls for input [MFC]
- user input [MFC], MFC control classes
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 376fb3836d92a1fae348929a7faa49b44dfd866e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="control-classes"></a>Denetim Sınıfları
Denetim sınıfları çok çeşitli statik metin denetimlerden ağaç denetimleri arasında değişen standart Windows denetimleri kapsüller. Ayrıca, MFC bit eşlemler ve denetim çubukları düğmeleriyle dahil olmak üzere bazı yeni denetimler sağlar.  
  
 Sınıf adları bitiş denetimleri "**Ctrl**" Windows 95 ve Windows NT sürüm 3.51'de yeni olan.  
  
## <a name="static-display-controls"></a>Statik görüntü denetimleri  
 [CStatic](../mfc/reference/cstatic-class.md)  
 Statik görüntü penceresi. Etiket, kutusunda veya başka bir iletişim kutusu veya pencere denetimlerinde ayırmak için kullanılan statik denetler. Ayrıca grafik görüntüleri yerine metin veya kutusu görüntüleyebilir.  
  
## <a name="text-controls"></a>Metin denetimleri  
 [CEdit](../mfc/reference/cedit-class.md)  
 Bir metin düzenlenebilir denetimi penceresini açın. Düzenleme denetimleri kullanıcı metinsel girişi kabul etmek için kullanılır.  
  
 [CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)  
 Bir Internet Protokolü (IP) adresi yönlendirmek için bir düzenleme kutusu destekler.  
  
 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)  
 Kullanıcı girin ve metin düzenleme denetimini. İçinde kapsüllenmiş denetimi tersine `CEdit`, bir zengin düzenleme denetimine karakter ve paragraf biçimlendirme ve OLE nesneleri destekler.  
  
## <a name="controls-that-represent-numbers"></a>Sayıları temsil eden denetimleri  
 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)  
 Bir değer veya değer kümesini seçmek için kullanıcı hareket bir kaydırıcı içeren bir denetimdir.  
  
 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)  
 Ok düğmelerini çifti artırın veya bir değer azaltma için kullanıcı tıklatabilirsiniz.  
  
 [CProgressCtrl](../mfc/reference/cprogressctrl-class.md)  
 Soldan sağa bir işlemin ilerlemesini göstermek için kademeli olarak doldurulmuş dikdörtgen görüntüler.  
  
 [CScrollBar](../mfc/reference/cscrollbar-class.md)  
 Kaydırma çubuğu denetimi penceresi. Sınıfı, bir iletişim kutusu veya penceresinde, kullanıcı bir aralıkta bir konum belirtebilirsiniz denetiminde olarak kullanmak üzere bir kaydırma çubuğunun işlevselliğini sağlar.  
  
## <a name="buttons"></a>Düğmeleri  
 [CButton](../mfc/reference/cbutton-class.md)  
 Düğme denetimi penceresi. Sınıfı, düğme, onay kutusu veya radyo düğmesi bir iletişim kutusu veya penceresinde programa dayalı bir arabirim sağlar.  
  
 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
 Bir metin resim yazısı yerine bir bit eşlem bir düğme.  
  
## <a name="lists"></a>Listeler  
 [CListBox](../mfc/reference/clistbox-class.md)  
 Liste kutusu denetimi penceresi. Liste kutusu, kullanıcının görüntüleyebileceği ve seçin öğeleri listesini görüntüler.  
  
 [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
 Bir Windows liste kutusu işlevselliğini sağlar; Liste kutusu içinde gibi dosya adları ve dize değişmez değerleri, liste kutusu öğeleri taşımak olanak tanır. Liste kutuları bu özelliğine sahip bir öğe listesi alfabetik daha başka bir sırada yararlıdır, gibi bir projede yol adları veya dosyaları içerir.  
  
 [CComboBox](../mfc/reference/ccombobox-class.md)  
 Birleşik giriş kutusu denetimi penceresi. Birleşik giriş kutusu düzenleme denetimi ve liste kutusu karakterlerinden oluşur.  
  
 [CComboBoxEx](../mfc/reference/ccomboboxex-class.md)  
 Birleşik giriş kutusu denetimi resim listeleri için destek sağlayarak genişletir.  
  
 [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
 Kullanıcı denetleyin veya temizleyin, her bir öğeyi yanındaki onay kutularını öğeleri listesini görüntüler.  
  
 [CListCtrl](../mfc/reference/clistctrl-class.md)  
 Öğeleri koleksiyonu, her bir simge ve dosya Explorer'ın sağ bölmeye benzer bir şekilde bir etiket oluşan görüntüler.  
  
 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)  
 Simgeler ve bir şekilde dosya Explorer'ın sol bölmeye benzer düzenlenmiş etiketleri hiyerarşik bir listesini görüntüler.  
  
## <a name="toolbars-and-status-bars"></a>Araç çubukları ve durum çubukları  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows ortak araç çubuğu denetimi işlevselliğini sağlar. Çoğu MFC programları kullanım [CToolBar](../mfc/reference/ctoolbar-class.md) yerine bu sınıf.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 Genellikle bir uygulama durum bilgilerini görüntüleyebilen bölmeye ayrılmış bir yatay penceresi. Çoğu MFC programları kullanım [CStatusBar](../mfc/reference/cstatusbar-class.md) yerine bu sınıf.  
  
## <a name="miscellaneous-controls"></a>Çeşitli denetimleri  
 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)  
 Basit bir video klip görüntüler.  
  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 Tek satırlık bir uygulamada bir aracı amacını açıklayan metin görüntüler küçük bir açılır pencere.  
  
 [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)  
 Genişletilmiş düzenleme denetimi veya bir kullanıcının belirli bir tarih veya saat değeri seçmesine izin veren basit bir takvim arabirimi denetimi destekler.  
  
 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)  
 Başlığı veya sütunların etiketlerini görüntüler.  
  
 [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)  
 Bir kullanıcının bir tarih seçin izin veren basit Takvim arabirimi denetimini destekler.  
  
 [CTabCtrl](../mfc/reference/ctabctrl-class.md)  
 Üzerinde kullanıcının, bir dizüstü bilgisayarın Bölücü benzer tıklatabileceği sekmelerle denetim.  
  
 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)  
 Kullanıcı bir eylem hızlı bir şekilde gerçekleştirmek için basabilirsiniz etkin bir tuş bileşimini oluşturmak kullanıcının sağlar.  
  
 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)  
 İşaretlenmiş metin oluşturur ve kullanıcının katıştırılmış bağlantıyı tıklattığında uygun uygulamaları başlatır.  
  
 [CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)  
 Bir MFC penceresinde WebBrowser ActiveX denetiminin işlevsellik sağlar.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 [Cımagelist](../mfc/reference/cimagelist-class.md)  
 Windows görüntü listesi işlevselliğini sağlar. Görüntü listeleri liste denetimleri ve ağaç denetimleri ile kullanılır. Depolamak ve bit eşlemler aynı boyuta sahip bir dizi arşivlemek için de kullanılabilir.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Windows denetimleriyle ilişkili tüm görünümleri için temel sınıf. Denetimlere bağlı görünümler aşağıda açıklanmıştır.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Bir Windows standart içeren bir görünüm düzenleme denetimi.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Zengin Windows içeren bir görünüm düzenleme denetimi.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows liste denetimi içeren bir görünüm.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows ağaç denetimi içeren bir görünüm.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

