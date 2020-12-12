---
description: 'Daha fazla bilgi edinin: denetimler (MFC)'
title: Denetimler (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
ms.openlocfilehash: 94406928741eecd00794dbde230effe4d89ab3f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310141"
---
# <a name="controls-mfc"></a>Denetimler (MFC)

Denetimler, kullanıcıların verileri girmek veya işlemek için etkileşime girebileceği nesnelerdir. Bunlar genellikle iletişim kutularında veya araç çubuklarında görünürler. Bu konu ailesi üç ana denetim türünü içerir:

- Sahip tarafından çizilmiş denetimler de dahil olmak üzere Windows ortak denetimleri

- ActiveX Denetimleri

- Microsoft Foundation Class Kitaplığı tarafından sağlanan diğer denetim sınıfları (MFC)

## <a name="windows-common-controls"></a>Windows ortak denetimleri

Windows işletim sistemi her zaman birkaç Windows ortak denetimi sağlamıştır. Bu denetim nesneleri programlanabilir ve Visual C++ iletişim kutusu Düzenleyicisi iletişim kutularınıza eklenmesini destekler. Microsoft Foundation Class Kitaplığı (MFC), [Windows ortak denetimleri ve MFC sınıfları](#_core_windows_common_controls_and_mfc_classes)tablosunda gösterildiği gibi bu denetimlerin her birini kapsülleyen sınıflar sağlar. (Tablodaki bazı öğelerin, daha fazla betimleyen ilgili konuları vardır. Konuların olmadığı denetimlerde, MFC sınıfının belgelerine bakın.)

Sınıf [CWnd](reference/cwnd-class.md) tüm denetim sınıfları dahil olmak üzere tüm pencere sınıflarının taban sınıfıdır.

## <a name="activex-controls"></a>ActiveX Denetimleri

Daha önce OLE denetimleri olarak bilinen ActiveX denetimleri, Windows için uygulamalarınızdaki iletişim kutularında veya World Wide Web HTML sayfalarında kullanılabilir. Daha fazla bilgi için bkz. [MFC ActiveX denetimleri](mfc-activex-controls.md).

## <a name="other-mfc-control-classes"></a>Diğer MFC denetim sınıfları

Tüm Windows ortak denetimlerini kapsülleyen ve kendi ActiveX denetimlerinizi programlamayı destekleyen sınıflara ek olarak (veya diğerleri tarafından sağlanan ActiveX denetimlerini kullanarak), MFC aşağıdaki denetim sınıflarını sağlar:

- [CBitmapButton](reference/cbitmapbutton-class.md)

- [CCheckListBox](reference/cchecklistbox-class.md)

- [CDragListBox](reference/cdraglistbox-class.md)

## <a name="finding-information-about-windows-common-controls"></a><a name="_core_finding_information_about_windows_common_controls"></a> Windows ortak denetimleriyle Ilgili bilgileri bulma

Aşağıdaki tabloda, denetimin MFC sarmalayıcı sınıfı dahil olmak üzere Windows ortak denetimlerinin her biri kısaca açıklanmaktadır.

### <a name="windows-common-controls-and-mfc-classes"></a><a name="_core_windows_common_controls_and_mfc_classes"></a> Windows ortak denetimleri ve MFC sınıfları

|Denetim|MFC sınıfı|Açıklama|Windows 95 ' de yeni|
|-------------|---------------|-----------------|------------------------|
|[unda](using-canimatectrl.md)|[CAnimateCtrl](reference/canimatectrl-class.md)|Bir AVI video klibinin ardışık çerçevelerini görüntüler|Evet|
|düğmesini seçin|[CButton](reference/cbutton-class.md)|Eyleme neden olan pushbuttons; onay kutuları, radyo düğmeleri ve Grup kutuları için de kullanılır|Hayır|
|birleşik giriş kutusu|[CComboBox](reference/ccombobox-class.md)|Düzenleme kutusu ve liste kutusu birleşimi|Hayır|
|[Tarih ve saat seçici](using-cdatetimectrl.md)|[CDateTimeCtrl](reference/cdatetimectrl-class.md)|Kullanıcının belirli bir tarih veya saat değeri seçmesine izin verir|Evet|
|düzenleme kutusu|[CEdit](reference/cedit-class.md)|Metin girme kutuları|Hayır|
|[Genişletilmiş Birleşik giriş kutusu](using-ccomboboxex.md)|[CComboBoxEx](reference/ccomboboxex-class.md)|Görüntüleri görüntüleme yeteneğine sahip bir Birleşik giriş kutusu denetimi|Evet|
|[üst bilgi](using-cheaderctrl.md)|[CHeaderCtrl](reference/cheaderctrl-class.md)|Metin sütununun üstünde görünen düğme; görünen metnin genişliğini denetler|Evet|
|[kısayol tuşu](using-chotkeyctrl.md)|[CHotKeyCtrl](reference/chotkeyctrl-class.md)|Kullanıcının bir eylemi hızlı bir şekilde gerçekleştirmek için "kısayol tuşu" oluşturmasını sağlayan pencere|Evet|
|[görüntü listesi](using-cimagelist.md)|[CImageList](reference/cimagelist-class.md)|Büyük simge veya bit eşlem kümelerini yönetmek için kullanılan görüntülerin toplanması (görüntü listesi gerçekten bir denetim değildir; diğer denetimler tarafından kullanılan listeleri destekler)|Evet|
|[list](using-clistctrl.md)|[CListCtrl](reference/clistctrl-class.md)|Simgeler içeren bir metin listesini görüntüleyen pencere|Evet|
|liste kutusu|[CListBox](reference/clistbox-class.md)|Dizelerin listesini içeren kutu|Hayır|
|[aylık takvim](using-cmonthcalctrl.md)|[CMonthCalCtrl](reference/cmonthcalctrl-class.md)|Tarih bilgilerini görüntüleyen denetim|Evet|
|[lemesine](using-cprogressctrl.md)|[CProgressCtrl](reference/cprogressctrl-class.md)|Uzun bir işlemin ilerlemesini gösteren pencere|Evet|
|[Rebar](using-crebarctrl.md)|[CRebarCtrl](reference/crebarctrl-class.md)|Denetim biçiminde ek alt pencereler içerebilen araç çubuğu|Evet|
|[zengin düzenleme](using-cricheditctrl.md)|[CRichEditCtrl](reference/cricheditctrl-class.md)|Kullanıcının karakter ve paragraf biçimlendirmesiyle düzenleyebileceği pencere (bkz. [zengin düzenleme denetimleriyle Ilgili sınıflar](classes-related-to-rich-edit-controls.md))|Evet|
|kaydırma çubuğu|[CScrollBar](reference/cscrollbar-class.md)|İletişim kutusu içinde denetim olarak kullanılan kaydırma çubuğu (pencerede değil)|Hayır|
|[sürgü](using-csliderctrl.md)|[CSliderCtrl](reference/csliderctrl-class.md)|İsteğe bağlı değer işaretleriyle kaydırıcı denetimi içeren pencere|Evet|
|[döndürme düğmesi](using-cspinbuttonctrl.md)|[CSpinButtonCtrl](reference/cspinbuttonctrl-class.md)|Bir değeri artırmak veya azaltmak için Kullanıcı tıklatabileceği ok düğmesi çifti|Evet|
|statik metin|[CStatic](reference/cstatic-class.md)|Diğer denetimlerin etiketlenmesi için metin|Hayır|
|[durum çubuğu](using-cstatusbarctrl.md)|[CStatusBarCtrl](reference/cstatusbarctrl-class.md)|MFC sınıfına benzer şekilde durum bilgilerini görüntülemek için pencere `CStatusBar`|Evet|
|[sekmesinde](using-ctabctrl.md)|[CTabCtrl](reference/ctabctrl-class.md)|Bir not defterindeki ayırıcıya benzer; "sekme iletişim kutularında" veya özellik sayfalarında kullanılır|Evet|
|[Toolbar](using-ctoolbarctrl.md)|[CToolBarCtrl](reference/ctoolbarctrl-class.md)|MFC sınıfına benzer şekilde, komut oluşturma düğmeleriyle pencere `CToolBar`|Evet|
|[Araç İpucu](using-ctooltipctrl.md)|[CToolTipCtrl](reference/ctooltipctrl-class.md)|Bir araç çubuğu düğmesi veya başka bir aracın amacını açıklayan küçük açılır pencere|Evet|
|[ağacının](using-ctreectrl.md)|[CTreeCtrl](reference/ctreectrl-class.md)|Öğelerin hiyerarşik listesini görüntüleyen pencere|Evet|

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- Bireysel denetim: tüm denetimlerin bağlantıları için bu konudaki [Windows ortak denetimleri ve MFC sınıfları](#_core_windows_common_controls_and_mfc_classes) tablosuna bakın

- [Denetimleri yapma ve kullanma](making-and-using-controls.md)

- [Denetim eklemek için iletişim kutusu düzenleyicisini kullanma](using-the-dialog-editor-to-add-controls.md)

- [İletişim kutusuna el ile denetim ekleme](adding-controls-by-hand.md)

- [MFC denetim sınıflarından denetim sınıfları türetme](deriving-controls-from-a-standard-control.md)

- [Alt pencereler olarak ortak denetimleri kullanma](using-a-common-control-as-a-child-window.md)

- [Ortak denetimlerden bildirimler](receiving-notification-from-common-controls.md)

- [İletişim kutusuna ortak denetimler ekleyin](using-common-controls-in-a-dialog-box.md).

- [Standart bir Windows denetiminden bir denetim türet](deriving-controls-from-a-standard-control.md)

- [Tür güvenliği olan iletişim kutusu denetimlerine erişin](type-safe-access-to-controls-in-a-dialog-box.md)

- [Ortak denetimlerden bildirim iletileri alma](receiving-notification-from-common-controls.md)

- [Örnekler](common-control-sample-list.md)

Windows SDK Windows ortak denetimleri hakkında daha fazla bilgi için bkz. [ortak denetimler](/windows/win32/Controls/common-controls-intro).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)<br/>
[İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)
