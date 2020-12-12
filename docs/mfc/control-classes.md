---
description: 'Daha fazla bilgi edinin: denetim sınıfları'
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
ms.openlocfilehash: eb0bee6d865867a052b5f49408bdaa1b70da343f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310128"
---
# <a name="control-classes"></a>Denetim Sınıfları

Denetim sınıfları statik metin denetimlerinden ağaç denetimlerine kadar değişen çok çeşitli standart Windows denetimlerini kapsüller. Ayrıca, MFC bit eşlemler ve denetim çubukları gibi bazı yeni denetimler de sağlar.

Sınıf adları "**CTRL**" ile biten denetimler Windows 95 ve Windows NT sürüm 3,51 ' de yenidir.

## <a name="static-display-controls"></a>Statik görüntü denetimleri

[CStatic](reference/cstatic-class.md)<br/>
Statik görüntü penceresi. Statik denetimler, bir iletişim kutusu veya penceredeki diğer denetimleri etiketlemek, kutuyu veya ayırmak için kullanılır. Ayrıca, metin veya kutu yerine grafik görüntüleri de görüntüleyebilir.

## <a name="text-controls"></a>Metin denetimleri

[CEdit](reference/cedit-class.md)<br/>
Düzenlenebilir metin denetim penceresi. Düzenleme denetimleri, kullanıcıdan metin girişi kabul etmek için kullanılır.

[CIPAddressCtrl](reference/cipaddressctrl-class.md)<br/>
Internet Protokolü (IP) adresini yönetmek için bir düzenleme kutusunu destekler.

[CRichEditCtrl](reference/cricheditctrl-class.md)<br/>
Kullanıcının metin girebileceği ve düzenleyebileceği bir denetim. İçinde kapsüllenmiş denetimin aksine `CEdit` , zengin bir düzenleme denetimi karakter ve paragraf biçimlendirme ve OLE nesnelerini destekler.

## <a name="controls-that-represent-numbers"></a>Sayıları temsil eden denetimler

[CSliderCtrl](reference/csliderctrl-class.md)<br/>
Kullanıcı bir değer veya değer kümesi seçmek için taşınan kaydırıcı içeren bir denetim.

[CSpinButtonCtrl](reference/cspinbuttonctrl-class.md)<br/>
Kullanıcının bir değeri artırmak veya azaltmak için tıklatabileceği bir çift ok düğmesi.

[CProgressCtrl](reference/cprogressctrl-class.md)<br/>
İşlemin ilerleme durumunu göstermek için soldan sağa doğru doldurulmuş bir dikdörtgen görüntüler.

[CScrollBar](reference/cscrollbar-class.md)<br/>
Bir kaydırma çubuğu denetim penceresi. Sınıfı, bir iletişim kutusu veya pencere içinde bir denetim olarak kullanım için, kullanıcının bir Aralık içinde konum belirtebileceğiniz bir kaydırma çubuğunun işlevlerini sağlar.

## <a name="buttons"></a>Düğmeler

[CButton](reference/cbutton-class.md)<br/>
Bir düğme denetim penceresi. Sınıfı, bir iletişim kutusu veya penceresinde bir Gönder düğmesi, onay kutusu veya radyo düğmesi için programlı bir arabirim sağlar.

[CBitmapButton](reference/cbitmapbutton-class.md)<br/>
Metin yazısı yerine bit eşlemle bir düğme.

## <a name="lists"></a>Listeler

[CListBox](reference/clistbox-class.md)<br/>
Liste kutusu denetim penceresi. Bir liste kutusu, kullanıcının görüntüleyebileceği ve seçebileceğiniz öğelerin bir listesini görüntüler.

[CDragListBox](reference/cdraglistbox-class.md)<br/>
Windows liste kutusu işlevlerini sağlar; kullanıcının liste kutusu içindeki dosya adları ve dize değişmez değerleri gibi liste kutusu öğelerini taşımasına izin verir. Bu özelliğe sahip liste kutuları bir öğe listesi için, bir proje içindeki yol adlarını veya dosyaları dahil olmak üzere alfabetik olmayan bir sıra için yararlıdır.

[CComboBox](reference/ccombobox-class.md)<br/>
Birleşik giriş kutusu denetim penceresi. Birleşik giriş kutusu, bir düzenleme denetiminden ve liste kutusundan oluşur.

[CComboBoxEx](reference/ccomboboxex-class.md)<br/>
Görüntü listeleri için destek sağlayarak Birleşik giriş kutusu denetimini genişletir.

[CCheckListBox](reference/cchecklistbox-class.md)<br/>
Kullanıcının her öğe için denetim veya temizleme yapabilir onay kutuları içeren bir öğe listesi görüntüler.

[CListCtrl](reference/clistctrl-class.md)<br/>
Dosya Gezgini 'nin sağ bölmesine benzer şekilde, her biri bir simge ve etiketten oluşan öğelerin koleksiyonunu görüntüler.

[CTreeCtrl](reference/ctreectrl-class.md)<br/>
Dosya Gezgini 'nin sol bölmesine benzer şekilde düzenlenmiş simge ve etiketlerin hiyerarşik bir listesini görüntüler.

## <a name="toolbars-and-status-bars"></a>Araç çubukları ve durum çubukları

[CToolBarCtrl](reference/ctoolbarctrl-class.md)<br/>
Windows Toolbar ortak denetiminin işlevlerini sağlar. Çoğu MFC programı bu sınıf yerine [CToolBar](reference/ctoolbar-class.md) kullanır.

[CStatusBarCtrl](reference/cstatusbarctrl-class.md)<br/>
Bir uygulamanın durum bilgilerini görüntüleyebilen, genellikle bölmelere ayrılmış yatay bir pencere. Çoğu MFC programı bu sınıf yerine [CStatusBar](reference/cstatusbar-class.md) kullanır.

## <a name="miscellaneous-controls"></a>Çeşitli denetimler

[CAnimateCtrl](reference/canimatectrl-class.md)<br/>
Basit bir video klibi görüntüler.

[CToolTipCtrl](reference/ctooltipctrl-class.md)<br/>
Uygulamadaki bir aracın amacını açıklayan tek satırlık bir metin görüntüleyen küçük bir açılır pencere.

[CDateTimeCtrl](reference/cdatetimectrl-class.md)<br/>
, Bir kullanıcının belirli bir tarih veya saat değeri seçmesini sağlayan bir genişletilmiş düzenleme denetimini ya da basit bir takvim arabirimi denetimini destekler.

[CHeaderCtrl](reference/cheaderctrl-class.md)<br/>
Sütunlar için başlıkları veya etiketleri görüntüler.

[CMonthCalCtrl](reference/cmonthcalctrl-class.md)<br/>
Kullanıcının bir tarih seçmesini sağlayan basit bir takvim arabirimi denetimini destekler.

[CTabCtrl](reference/ctabctrl-class.md)<br/>
Bir not defterindeki ayırıcılarla benzer şekilde, kullanıcının tıklabileceği sekmeler içeren bir denetim.

[CHotKeyCtrl](reference/chotkeyctrl-class.md)<br/>
Kullanıcının bir eylem gerçekleştirmek için hızlı bir şekilde kullanılabilecek bir kısayol tuş bileşimi oluşturmasını sağlar.

[CLinkCtrl](reference/clinkctrl-class.md)<br/>
İşaretlenen metni işler ve Kullanıcı katıştırılmış bağlantıyı tıklattığında uygun uygulamaları başlatır.

[CHtmlEditCtrl](reference/chtmleditctrl-class.md)<br/>
Bir MFC penceresinde WebBrowser ActiveX denetiminin işlevlerini sağlar.

## <a name="related-classes"></a>İlgili sınıflar

[CImageList](reference/cimagelist-class.md)<br/>
Windows görüntü listesi işlevlerini sağlar. Görüntü listeleri liste denetimleri ve ağaç denetimleriyle birlikte kullanılır. Aynı zamanda aynı boyutlu bit eşlemlerin bir kümesini depolamak ve arşivlemek için de kullanılabilir.

[CCtrlView](reference/cctrlview-class.md)<br/>
Windows denetimleriyle ilişkili tüm görünümlerin temel sınıfı. Denetimleri temel alan görünümler aşağıda açıklanmıştır.

[CEditView](reference/ceditview-class.md)<br/>
Windows standart düzenleme denetimi içeren bir görünüm.

[CRichEditView](reference/cricheditview-class.md)<br/>
Windows zengin düzenleme denetimi içeren bir görünüm.

[CListView](reference/clistview-class.md)<br/>
Windows liste denetimi içeren bir görünüm.

[CTreeView karşılaştırması](reference/ctreeview-class.md)<br/>
Windows ağaç denetimi içeren bir görünüm.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
