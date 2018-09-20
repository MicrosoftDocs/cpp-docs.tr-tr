---
title: Denetimler (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3607af849b1e395a0a467bcdbe65a2763fb3603
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405066"
---
# <a name="controls-mfc"></a>Denetimler (MFC)

Denetimler, kullanıcıları girin ya da verileri işlemek için etkileşim kurabilir nesneleridir. Sık iletişim kutularında veya araç çubuklarındaki görünürler. Bu konuda ailesi üç ana denetim türlerinin kapsar:

- Kullanıcı çizimli denetimler de dahil olmak üzere Windows ortak denetimleri

- ActiveX Denetimleri

- Microsoft Foundation Class Kitaplığı (MFC) tarafından sağlanan diğer denetim sınıfları

## <a name="windows-common-controls"></a>Windows ortak denetimleri

Windows işletim sistemi, her zaman Windows ortak denetimleri sayısı sağlamıştır. Bu denetimi nesnelerini programlanabilir ve bunları, iletişim kutularına ekleme iletişim kutusu Düzenleyicisi Visual C++ destekler. Tabloda gösterildiği gibi bu denetimlerin her birinden yalıtan sınıflar Microsoft Foundation Class Kitaplığı'nı (MFC) sağladığı [Windows ortak denetimleri ve MFC sınıfları](#_core_windows_common_controls_and_mfc_classes). (Tablo içindeki bazı öğeler daha fazla açıklayan konuların ilgili. Konuları eksik denetimleri için MFC sınıfı belgelerine bakın.)

Sınıf [CWnd](../mfc/reference/cwnd-class.md) tüm denetim sınıfları da dahil olmak üzere tüm pencere sınıflarının temel sınıftır.

## <a name="activex-controls"></a>ActiveX Denetimleri

ActiveX denetimleri, eski adı OLE denetimleri bilinen, iletişim kutularında uygulamalarınızı Windows veya HTML World Wide Web sayfalarında kullanılabilir. Daha fazla bilgi için [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md).

## <a name="other-mfc-control-classes"></a>Diğer MFC denetim sınıfları

Windows ortak denetimleri ve söz konusu destek kendi ActiveX denetimlerini programlama (veya başkaları tarafından sağlanan ActiveX denetimlerini kullanarak) tüm kapsayan sınıflarının yanı sıra MFC, kendine ait aşağıdaki denetim sınıfları sağlar:

- [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)

- [CCheckListBox](../mfc/reference/cchecklistbox-class.md)

- [CDragListBox](../mfc/reference/cdraglistbox-class.md)

##  <a name="_core_finding_information_about_windows_common_controls"></a> Windows ortak denetimleri hakkında bilgi bulma

Aşağıdaki tabloda kısaca denetim MFC sarmalayıcı sınıfı dahil olmak üzere Windows ortak denetimleri açıklar.

### <a name="_core_windows_common_controls_and_mfc_classes"></a>  Windows ortak denetimleri ve MFC sınıfları

|Denetim|MFC sınıfı|Açıklama|Windows 95'te yeni eklendi|
|-------------|---------------|-----------------|------------------------|
|[Animasyon](../mfc/using-canimatectrl.md)|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|AVI video klibinin art arda çerçeveleri görüntüler|Evet|
|Düğme|[CButton](../mfc/reference/cbutton-class.md)|Bir eylemin gerçekleşmesini pushbuttons; onay kutuları, radyo düğmeleri ve Grup kutuları için de kullanılır|Hayır|
|birleşik giriş kutusu|[CComboBox](../mfc/reference/ccombobox-class.md)|Düzenleme kutusu ve liste kutusu|Hayır|
|[Tarih ve Saat Seçici](../mfc/using-cdatetimectrl.md)|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|Kullanıcının belirli bir tarih veya saat değeri seçmesine izin verir|Evet|
|Düzenleme kutusu|[CEdit](../mfc/reference/cedit-class.md)|Giriş metin kutuları|Hayır|
|[Genişletilmiş Birleşik giriş kutusu](../mfc/using-ccomboboxex.md)|[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)|Bir birleşik giriş kutusu denetimi ile görüntüleri görüntüleme|Evet|
|[Üst bilgi](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)|Metin içeren bir sütun üzerinde görüntülenen düğme; görüntülenen metin denetim genişliği|Evet|
|[Kısayol tuşu](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|"Sık kullanılan tuş" oluşturmasına olanak sağlayan bir pencere hızlı bir eylem gerçekleştirmek için|Evet|
|[görüntü listesi](../mfc/using-cimagelist.md)|[Cımagelist](../mfc/reference/cimagelist-class.md)|Büyük simgeler veya bit eşlemler kümelerini yönetmek için kullanılan görüntü koleksiyonunu (görüntü listesi değil gerçekten bir denetimi; diğer denetimleri tarafından kullanılan listelerini destekler)|Evet|
|[list](../mfc/using-clistctrl.md)|[CListCtrl](../mfc/reference/clistctrl-class.md)|Simgeleri içeren bir metin listesini görüntüleyen pencere|Evet|
|Liste kutusu|[CListBox](../mfc/reference/clistbox-class.md)|İçeren bir dize listesi kutusu|Hayır|
|[Aylık takvim](../mfc/using-cmonthcalctrl.md)|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|Tarih bilgileri görüntüleyen denetimi|Evet|
|[İlerleme durumu](../mfc/using-cprogressctrl.md)|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Uzun bir işlemin ilerlemesini gösteren penceresi|Evet|
|[Çubuk barınağı](../mfc/using-crebarctrl.md)|[CRebarCtrl](../mfc/reference/crebarctrl-class.md)|Ek alt pencereleri biçiminde denetimleri içerebilen araç çubuğu|Evet|
|[Zengin düzenleme](../mfc/using-cricheditctrl.md)|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|Hangi kullanıcı penceresinde karakter ve paragraf biçimlendirme düzenleyebilir (bkz [zengin düzenleme denetimleri ilgili sınıflar](../mfc/classes-related-to-rich-edit-controls.md))|Evet|
|kaydırma çubuğu|[CScrollBar](../mfc/reference/cscrollbar-class.md)|Bir iletişim kutusu (değil, bir pencere) içindeki bir denetim olarak kullanılan kaydırma çubuğu|Hayır|
|[Kaydırıcı](../mfc/using-csliderctrl.md)|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|İsteğe bağlı bir kaydırıcı denetimi içeren pencere onay işaretleri|Evet|
|[değer değiştirme düğmesi](../mfc/using-cspinbuttonctrl.md)|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Çift ok düğmelerini kullanıcı basamağa tıklayabilir veya bir değeri Azalt|Evet|
|statik metin|[CStatic](../mfc/reference/cstatic-class.md)|Diğer denetimleri etiketleme metin|Hayır|
|[Durum çubuğu](../mfc/using-cstatusbarctrl.md)|[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)|MFC sınıfına benzer durum bilgilerini görüntülemeye penceresi `CStatusBar`|Evet|
|[sekmesi](../mfc/using-ctabctrl.md)|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Bir not defterinde Bölücü benzer; "iletişim kutusu" veya özellik sayfaları|Evet|
|[Araç çubuğu](../mfc/using-ctoolbarctrl.md)|[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)|Komut oluşturma penceresiyle düğmeler, benzer şekilde MFC sınıfı `CToolBar`|Evet|
|[Araç İpucu](../mfc/using-ctooltipctrl.md)|[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)|Araç çubuğu düğmesini veya diğer aracı amacını açıklayan küçük bir açılır pencere|Evet|
|[Ağaç](../mfc/using-ctreectrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Hiyerarşik öğeleri listesini görüntüleyen pencere|Evet|

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- Tek bir denetim: tabloya bakın [Windows ortak denetimleri ve MFC sınıfları](#_core_windows_common_controls_and_mfc_classes) bağlantıları tüm denetimler için bu konudaki

- [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)

- [Denetim eklemek için iletişim kutusu düzenleyicisini kullanma](../mfc/using-the-dialog-editor-to-add-controls.md)

- [El ile iletişim kutusuna denetim ekleme](../mfc/adding-controls-by-hand.md)

- [Denetim sınıfları MFC denetim sınıflarından türetme](../mfc/deriving-controls-from-a-standard-control.md)

- [Alt öğe pencerelerini ortak denetimleri kullanma](../mfc/using-a-common-control-as-a-child-window.md)

- [Ortak denetimlerden bildirim](../mfc/receiving-notification-from-common-controls.md)

- [Ortak denetimleri Ekle iletişim kutusuna](../mfc/using-common-controls-in-a-dialog-box.md).

- [Bir denetim standart bir Windows denetiminden türetilen](../mfc/deriving-controls-from-a-standard-control.md)

- [Tür güvenliği ile erişimi iletişim kutusu denetimleri](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Ortak denetimlerden bildirim iletilerini alma](../mfc/receiving-notification-from-common-controls.md)

- [Örnekler](../mfc/common-control-sample-list.md)

Windows SDK'sındaki Windows ortak denetimleri hakkında daha fazla bilgi için bkz. [ortak denetimleri](/windows/desktop/Controls/common-controls-intro).

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

