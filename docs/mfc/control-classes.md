---
title: Denetim Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
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
ms.openlocfilehash: 79a71a4660cd49f85726d730c9fad0b2f10f83bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338174"
---
# <a name="control-classes"></a>Denetim Sınıfları

Denetim sınıfları, standart Windows denetimleri için ağaç denetimleri statik metin denetimlerinden arasında değişen birçok farklı kapsüller. Ayrıca, MFC, bit eşlemler ve denetim çubukları düğmeleriyle dahil olmak üzere bazı yeni denetimler sağlar.

Denetimleri, sınıf adlarının sonunda içinde "**Ctrl**" Windows 95 ve Windows NT 3.51 sürümü yeni bulabilirsiniz.

## <a name="static-display-controls"></a>Statik görüntü denetimleri

[CStatic](../mfc/reference/cstatic-class.md)<br/>
Statik görüntü penceresi. Statik denetim, Etiket kutusuna ya da diğer denetimler iletişim kutusunda veya pencere ayırmak için kullanılır. Grafik görüntüleri yerine metin veya kutusu da görüntülenebilir.

## <a name="text-controls"></a>Metin denetimi

[CEdit](../mfc/reference/cedit-class.md)<br/>
Bir düzenlenebilir metin denetimi penceresi. Düzenleme denetimleri, metin girişi kullanıcıdan kabul etmek için kullanılır.

[Cıpaddressctrl](../mfc/reference/cipaddressctrl-class.md)<br/>
Bir Internet Protokolü (IP) adresi işlemek için bir düzenleme kutusuna destekler.

[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)<br/>
Kullanıcı girin ve metin düzenleme denetimi. Aksine, kapsüllenmiş denetimi `CEdit`, karakter ve paragraf biçimlendirme ve OLE nesneleri bir zengin düzenleme denetimini destekler.

## <a name="controls-that-represent-numbers"></a>Sayıları temsil denetimleri

[CSliderCtrl](../mfc/reference/csliderctrl-class.md)<br/>
Bir kaydırıcı değeri veya değerleri kümesi seçmek için kullanıcı hareket içeren bir denetimdir.

[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)<br/>
Bir çift ok düğmelerini azaltabilir ya da bir değer azaltma için kullanıcı tıklayabilirsiniz.

[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)<br/>
Soldan sağa bir işlemin ilerlemesini belirtmek için kademeli olarak doldurulmuş bir dikdörtgen görüntüler.

[CScrollBar](../mfc/reference/cscrollbar-class.md)<br/>
Bir kaydırma çubuğu denetimi penceresi. Sınıfı, bir iletişim kutusu veya kullanıcı bir aralık içinde bir konum belirtebilirsiniz penceresinde denetimi olarak kullanılmak üzere bir kaydırma çubuğunun işlevlerini sağlar.

## <a name="buttons"></a>Düğmeler

[CButton](../mfc/reference/cbutton-class.md)<br/>
Bir düğme denetimi penceresi. Sınıf, düğme, onay kutusu veya radyo düğmesinin bir iletişim kutusu veya penceresi için bir programlama arabirimi sağlar.

[CBitmapButton](../mfc/reference/cbitmapbutton-class.md)<br/>
Başlık metnini yerine bir bit eşlem ile bir düğme.

## <a name="lists"></a>Listeler

[CListBox](../mfc/reference/clistbox-class.md)<br/>
Bir liste kutusu denetimi penceresi. Liste kutusu, kullanıcının görüntüleyebileceği ve Seç öğeleri listesini görüntüler.

[CDragListBox](../mfc/reference/cdraglistbox-class.md)<br/>
Windows liste kutusu işlevlerini sağlar. dosya adları ve dize değişmez değerleri gibi liste kutusu öğelerini taşımasına izin verir. Liste kutuları bu özelliğe sahip bir öğe listesi alfabetik değerinden başka bir sırada için yararlıdır, yol adlarını veya dosyaları gibi bir proje içerir.

[CComboBox](../mfc/reference/ccombobox-class.md)<br/>
Bir birleşik giriş kutusu denetimi penceresi. Birleşik giriş kutusu, bir düzenleme denetimi ve liste kutusu karakterlerinden oluşur.

[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)<br/>
Birleşik giriş kutusu denetim görüntü listeleri için destek sağlayarak genişletir.

[CCheckListBox](../mfc/reference/cchecklistbox-class.md)<br/>
Hangi kullanıcı işaretleyin veya işaretini kaldırın, her öğesinin yanında onay kutuları öğelerin listesini görüntüler.

[CListCtrl](../mfc/reference/clistctrl-class.md)<br/>
Bir öğe koleksiyonu, her bir simge ve dosya Gezgini'nin sağ bölmeye benzer bir şekilde bir etiket oluşan görüntüler.

[CTreeCtrl](../mfc/reference/ctreectrl-class.md)<br/>
Simgelerin ve etiketlerin bir şekilde dosya Gezgini için sol bölmedeki benzer düzenlenmiş, hiyerarşik bir listesini görüntüler.

## <a name="toolbars-and-status-bars"></a>Araç çubuklarını ve durum çubukları

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Windows ortak araç çubuğu denetimi işlevlerini sağlar. Çoğu MFC programları kullanım [CToolBar](../mfc/reference/ctoolbar-class.md) yerine bu sınıfı.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Yatay bir pencere genellikle uygulama durum bilgilerini görüntüleyebilen bölmelere bölünür. Çoğu MFC programları kullanım [CStatusBar](../mfc/reference/cstatusbar-class.md) yerine bu sınıfı.

## <a name="miscellaneous-controls"></a>Çeşitli denetimleri

[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)<br/>
Basit bir video klibi görüntüler.

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Bir uygulamada bir aracın amacını açıklayan metnin tek bir çizgi görüntüler küçük bir açılır pencere.

[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)<br/>
Bir genişletilmiş düzenleme denetimi ya da bir kullanıcının belirli bir tarih veya saat değeri seçmenizi sağlayan bir basit Takvim arabirimi denetimini destekler.

[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)<br/>
Başlıklar ve etiketler sütunlar için görüntüler.

[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)<br/>
Kullanıcının tarih seçmesini sağlayan bir basit bir takvim arabirimi denetimini destekler.

[CTabCtrl](../mfc/reference/ctabctrl-class.md)<br/>
Bir denetimi sekmeli üzerinde kullanıcı, bir dizüstü bilgisayarın Bölücü benzer tıklayabilirsiniz.

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)<br/>
Hızlı bir eylem gerçekleştirmek için kullanıcı basabilirsiniz sık erişimli bir tuş bileşimi oluşturmak kullanıcının sağlar.

[CLinkCtrl](../mfc/reference/clinkctrl-class.md)<br/>
İşaretlenmiş metin işler ve kullanıcı katıştırılmış bağlantısına tıkladığında ilgili uygulamaları başlatır.

[CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)<br/>
Bir MFC penceresindeki WebBrowser ActiveX denetimi işlevlerini sağlar.

## <a name="related-classes"></a>İlgili sınıflar

[Cımagelist](../mfc/reference/cimagelist-class.md)<br/>
Windows görüntü listesinin işlevlerini sağlar. Görüntü listeleri liste denetimleri ve ağaç denetimleri ile kullanılır. Depolama ve bit eşlemleri aynı boyutlu bir dizi arşivlemek için de kullanılabilir.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows denetimleri ile ilgili tüm görünümleri için temel sınıf. Denetimlerine göre görünümleri aşağıda açıklanmıştır.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Bir Windows standart içeren bir görünümü düzenleme denetimi.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Zengin bir Windows içeren bir görünümü düzenleme denetimi.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows liste denetimi içeren bir görünüm.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Bir Windows ağaç denetimi içeren bir görünüm.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
