---
title: Denetimler (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
ms.openlocfilehash: 454a76e8fdf55f43d75abb63d7d98a9fe4926127
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365322"
---
# <a name="controls-mfc"></a>Denetimler (MFC)

Denetimler, kullanıcıların verileri girmek veya işlemek için etkileşimde bulunabilir nesnelerdir. Genellikle iletişim kutularında veya araç çubuklarında görünürler. Bu konu ailesi üç ana denetim çeşidini kapsar:

- Sahip tarafından çizilen denetimler de dahil olmak üzere Windows ortak denetimleri

- ActiveX Denetimleri

- Microsoft Foundation Class Library (MFC) tarafından sağlanan diğer denetim sınıfları

## <a name="windows-common-controls"></a>Windows Ortak Denetimleri

Windows işletim sistemi her zaman windows ortak denetimleri bir dizi sağlamıştır. Bu denetim nesneleri programlanabilir ve Visual C++ iletişim düzenleyicisi bunları iletişim kutularınıza eklemeyi destekler. Microsoft Hazırlık Sınıf Kitaplığı (MFC), [windows ortak denetimleri ve MFC Sınıfları](#_core_windows_common_controls_and_mfc_classes)tablosunda gösterildiği gibi, bu denetimlerin her birini kapsülleyen sınıflar sağlar. (Tablodaki bazı öğelerin, bunları daha fazla tanımlayan ilgili konuları vardır. Konu bulunmayan denetimler için MFC sınıfıiçin belgelere bakın.)

[CWnd](../mfc/reference/cwnd-class.md) sınıfı, tüm denetim sınıfları da dahil olmak üzere tüm pencere sınıflarının taban sınıfıdır.

## <a name="activex-controls"></a>ActiveX Denetimleri

Eskiden OLE denetimleri olarak bilinen ActiveX denetimleri, Windows uygulamalarınızdaki iletişim kutularında veya World Wide Web'deki HTML sayfalarında kullanılabilir. Daha fazla bilgi için [MFC ActiveX Denetimleri'ne](../mfc/mfc-activex-controls.md)bakın.

## <a name="other-mfc-control-classes"></a>Diğer MFC Kontrol Sınıfları

Tüm Windows ortak denetimlerini kapsülleyen ve kendi ActiveX denetimlerinizi programlamayı destekleyen (veya başkaları tarafından sağlanan ActiveX denetimlerini kullanan) sınıflara ek olarak, MFC kendi denetim sınıflarını sağlar:

- [Cbitmapbutton](../mfc/reference/cbitmapbutton-class.md)

- [CCheckListBox](../mfc/reference/cchecklistbox-class.md)

- [CDragListBox](../mfc/reference/cdraglistbox-class.md)

## <a name="finding-information-about-windows-common-controls"></a><a name="_core_finding_information_about_windows_common_controls"></a>Windows Ortak Denetimleri Hakkında Bilgi Bulma

Aşağıdaki tabloda, denetimin MFC sarıcı sınıfı da dahil olmak üzere Windows ortak denetimlerinin her biri kısaca açıklanmaktadır.

### <a name="windows-common-controls-and-mfc-classes"></a><a name="_core_windows_common_controls_and_mfc_classes"></a>Windows Ortak Denetimleri ve MFC Sınıfları

|Denetim|MFC sınıfı|Açıklama|Windows 95'te yeni|
|-------------|---------------|-----------------|------------------------|
|[Animasyon](../mfc/using-canimatectrl.md)|[Canimatectrl](../mfc/reference/canimatectrl-class.md)|AVI video klibinin art arda karelerini görüntüler|Evet|
|düğmesini seçin|[Cbutton](../mfc/reference/cbutton-class.md)|Eyleme neden olan düğmeler; onay kutuları, radyo düğmeleri ve grup kutuları için de kullanılır|Hayır|
|birleşik giriş kutusu|[Ccombobox](../mfc/reference/ccombobox-class.md)|Bir edit kutusu ve liste kutusunun birleşimi|Hayır|
|[tarih ve saat seçici](../mfc/using-cdatetimectrl.md)|[Cdatetimectrl](../mfc/reference/cdatetimectrl-class.md)|Kullanıcının belirli bir tarih veya saat değeri seçmesine izin verir|Evet|
|kutuyu edit|[Cedit](../mfc/reference/cedit-class.md)|Metin girmek için kutular|Hayır|
|[genişletilmiş açılan kutu](../mfc/using-ccomboboxex.md)|[Ccomboboxex](../mfc/reference/ccomboboxex-class.md)|Görüntüleri görüntüleme özelliğine sahip açılan kutu kontrolü|Evet|
|[Üstbilgi](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)|Bir metin sütununun üzerinde görünen düğme; görüntülenen metnin genişliğini denetler|Evet|
|[Hotkey](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Kullanıcının bir eylemi hızlı bir şekilde gerçekleştirmek için "sıcak anahtar" oluşturmasını sağlayan pencere|Evet|
|[resim listesi](../mfc/using-cimagelist.md)|[Cımagelist](../mfc/reference/cimagelist-class.md)|Büyük simge kümelerini veya bit eşlemi leri yönetmek için kullanılan görüntülerin toplanması (resim listesi gerçekten bir denetim değildir; diğer denetimler tarafından kullanılan listeleri destekler)|Evet|
|[list](../mfc/using-clistctrl.md)|[Clistctrl](../mfc/reference/clistctrl-class.md)|Simgeli bir metin listesini görüntüleyen pencere|Evet|
|liste kutusu|[Clistbox](../mfc/reference/clistbox-class.md)|Dizeleri listesini içeren kutu|Hayır|
|[aylık takvim](../mfc/using-cmonthcalctrl.md)|[Cmonthcalctrl](../mfc/reference/cmonthcalctrl-class.md)|Tarih bilgilerini görüntüleyen denetim|Evet|
|[Ilerleme](../mfc/using-cprogressctrl.md)|[Cprogressctrl](../mfc/reference/cprogressctrl-class.md)|Uzun bir işlemin ilerlemesini gösteren pencere|Evet|
|[Nervürlü](../mfc/using-crebarctrl.md)|[Crebarctrl](../mfc/reference/crebarctrl-class.md)|Denetimler biçiminde ek alt pencereler içerebilen araç çubuğu|Evet|
|[zengin edit](../mfc/using-cricheditctrl.md)|[Cricheditctrl](../mfc/reference/cricheditctrl-class.md)|Kullanıcının karakter ve paragraf biçimlendirmesiyle değiştirebileceği pencere (bkz. [Zengin Edit Denetimleri ile İlgili Sınıflar)](../mfc/classes-related-to-rich-edit-controls.md)|Evet|
|kaydırma çubuğu|[Cscrollbar](../mfc/reference/cscrollbar-class.md)|İletişim kutusunun içinde denetim olarak kullanılan kaydırma çubuğu (pencerede değil)|Hayır|
|[Kaydırıcı](../mfc/using-csliderctrl.md)|[Csliderctrl](../mfc/reference/csliderctrl-class.md)|İsteğe bağlı onay işaretleriiçeren kaydırıcı denetimi içeren pencere|Evet|
|[döndürme düğmesi](../mfc/using-cspinbuttonctrl.md)|[Cspinbuttonctrl](../mfc/reference/cspinbuttonctrl-class.md)|Ok düğmeleri kullanıcı artış veya bir değer verme için tıklayabilirsiniz çifti|Evet|
|statik metin|[Cstatic](../mfc/reference/cstatic-class.md)|Diğer denetimleri etiketlemek için metin|Hayır|
|[durum çubuğu](../mfc/using-cstatusbarctrl.md)|[Cstatusbarctrl](../mfc/reference/cstatusbarctrl-class.md)|MFC sınıfına benzer durum bilgilerini görüntüleme penceresi`CStatusBar`|Evet|
|[Sekme](../mfc/using-ctabctrl.md)|[Ctabctrl](../mfc/reference/ctabctrl-class.md)|Not defterindeki bölücülere benzer; "sekme iletişim kutuları" veya özellik sayfalarında kullanılır|Evet|
|[Araç çubuğu](../mfc/using-ctoolbarctrl.md)|[Ctoolbarctrl](../mfc/reference/ctoolbarctrl-class.md)|MFC sınıfına benzer komut oluşturma düğmelerine sahip pencere`CToolBar`|Evet|
|[araç ucu](../mfc/using-ctooltipctrl.md)|[Ctooltipctrl](../mfc/reference/ctooltipctrl-class.md)|Araç çubuğu düğmesinin veya başka bir aracın amacını açıklayan küçük açılır pencere|Evet|
|[ağaç](../mfc/using-ctreectrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Öğelerin hiyerarşik listesini görüntüleyen pencere|Evet|

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- Bireysel denetim: Tüm denetimlere bağlantılar için bu konuda [tabloya Windows Ortak Denetimleri ve MFC Sınıfları'na](#_core_windows_common_controls_and_mfc_classes) bakın

- [Denetim oluşturma ve kullanma](../mfc/making-and-using-controls.md)

- [Denetim eklemek için iletişim düzenleyicisini kullanma](../mfc/using-the-dialog-editor-to-add-controls.md)

- [İletişim kutusuna denetimleri elle ekleme](../mfc/adding-controls-by-hand.md)

- [MFC denetim sınıflarından denetim sınıfları alma](../mfc/deriving-controls-from-a-standard-control.md)

- [Ortak denetimleri alt pencere olarak kullanma](../mfc/using-a-common-control-as-a-child-window.md)

- [Ortak denetimlerden gelen bildirimler](../mfc/receiving-notification-from-common-controls.md)

- [İletişim kutusuna sık kullanılan denetimler ekleyin.](../mfc/using-common-controls-in-a-dialog-box.md)

- [Standart bir Windows denetiminden denetim elde etme](../mfc/deriving-controls-from-a-standard-control.md)

- [Tür güvenliği yle iletişim kutusu denetimlerini erişin](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Sık kullanılan denetimlerden bildirim iletileri alma](../mfc/receiving-notification-from-common-controls.md)

- [Örnekler](../mfc/common-control-sample-list.md)

Windows SDK'daki Windows ortak denetimleri hakkında daha fazla bilgi için [Bkz. Ortak Denetimler.](/windows/win32/Controls/common-controls-intro)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Elemanları](../mfc/user-interface-elements-mfc.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)
