---
title: Denetimler (MFC) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fd146ecd4a5c1b431ea63a98e770b0cb2e0917d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="controls-mfc"></a>Denetimler (MFC)
Kullanıcıları girin ya da verileri işlemek için etkileşim kurabildikleri nesneleri denetimleridir. Bunlar genellikle iletişim kutularında veya araç çubukları görüntülenir. Bu konuda ailesi denetimleri üç ana türlerini kapsar:  
  
-   Sahip tarafından çizilmiş denetimler de dahil olmak üzere Windows ortak denetimleri  
  
-   ActiveX Denetimleri  
  
-   Microsoft Foundation Class Kitaplığı (MFC) tarafından sağlanan diğer denetim sınıfları  
  
## <a name="windows-common-controls"></a>Windows ortak denetimleri  
 Windows işletim sistemi her zaman Windows ortak denetimleri sayısı sağlamıştır. Bu denetim nesneleri programlanabilir ve iletişim kutularına ekleme Visual C++ iletişim kutusu Düzenleyicisi'ni destekler. Tabloda gösterildiği gibi Microsoft Foundation Class Kitaplığı (MFC) bu denetimlerin her birinin kapsülleyen sınıflar sağlar [Windows ortak denetimleri ve MFC sınıfları](#_core_windows_common_controls_and_mfc_classes). (Bazı öğeler tablosundaki başka açıklayan konulara ilgili. Konular eksikliği denetimleri için MFC sınıfı belgelerine bakın.)  
  
 Sınıf [CWnd](../mfc/reference/cwnd-class.md) tüm denetim sınıfları dahil olmak üzere tüm pencere sınıfların temel sınıftır. Windows ortak denetimleri aşağıdaki ortamlarda desteklenir:  
  
-   Windows 95, Windows 98 ve Windows 2000  
  
-   Windows NT 3.51 ve sonraki sürümleri  
  
-   Win32, sürüm 1.3 (Visual C++'ın 4.2 ve sonraki sürümleri Win32 desteklemez)  
  
 Eski ortak denetimler — onay kutularını, birleşik giriş kutuları Düzenle kutuları, liste kutuları, seçenek düğmeleri, pushbuttons, kaydırma çubuğu denetimleri ve statik denetimleri — daha önceki Windows sürümlerinde de kullanılabilir durumdadır.  
  
## <a name="activex-controls"></a>ActiveX Denetimleri  
 ActiveX denetimleri, önceden OLE denetimi olarak bilinen iletişim kutularında uygulamalarınızın Windows veya HTML sayfaları World Wide Web'de kullanılabilir. Daha fazla bilgi için bkz: [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md).  
  
## <a name="other-mfc-control-classes"></a>Diğer MFC denetim sınıfları  
 Tüm Windows ortak denetimleri ve bu destek, kendi ActiveX denetimlerini programlama (veya başkaları tarafından sağlanan ActiveX denetimlerini kullanarak) kapsülleyen sınıflar ek olarak, MFC kendi aşağıdaki denetim sınıfları sağlar:  
  
-   [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)  
  
-   [CCheckListBox](../mfc/reference/cchecklistbox-class.md)  
  
-   [CDragListBox](../mfc/reference/cdraglistbox-class.md)  
  
##  <a name="_core_finding_information_about_windows_common_controls"></a>Windows ortak denetimleri hakkında bilgi bulma  
 Aşağıdaki tabloda her denetimin MFC sarmalayıcı sınıfı dahil olmak üzere Windows ortak denetimleri kısaca açıklanmaktadır.  
  
### <a name="_core_windows_common_controls_and_mfc_classes"></a>Windows ortak denetimleri ve MFC sınıfları  
  
|Denetim|MFC sınıfı|Açıklama|Windows 95'de yeni|  
|-------------|---------------|-----------------|------------------------|  
|[animasyon](../mfc/using-canimatectrl.md)|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Bir AVI video klip, art arda çerçeveleri görüntüler|Evet|  
|Düğmesi|[CButton](../mfc/reference/cbutton-class.md)|Bir eylemin gerçekleşmesini pushbuttons; onay kutuları, radyo düğmeleri ve Grup kutuları için de kullanılır|Hayır|  
|birleşik giriş kutusu|[CComboBox](../mfc/reference/ccombobox-class.md)|Düzenleme kutusu ve liste kutusu birleşimi|Hayır|  
|[Tarih ve Saat Seçici](../mfc/using-cdatetimectrl.md)|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|Kullanıcının belirli bir tarih veya saat değeri seçmesine izin verir|Evet|  
|Düzenleme kutusu|[CEdit](../mfc/reference/cedit-class.md)|Metin girerek kutuları|Hayır|  
|[Genişletilmiş Birleşik giriş kutusu](../mfc/using-ccomboboxex.md)|[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)|Birleşik giriş kutusu denetimi resimleri görüntüleme olanağı|Evet|  
|[Üstbilgi](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)|Bir metin sütunu görünür düğme; görüntülenen metin genişliğini denetler|Evet|  
|[kısayol tuşu](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|"Sık kullanılan tuş" oluşturmak kullanıcının sağlayan penceresi hızlı bir şekilde bir eylemi gerçekleştirmek için|Evet|  
|[Resim Listesi](../mfc/using-cimagelist.md)|[Cımagelist](../mfc/reference/cimagelist-class.md)|Simgeler veya bit eşlemler büyük kümelerini yönetmek için kullanılan görüntü koleksiyonu (resim listesi denetim gerçekten değildir; diğer denetimler tarafından kullanılan listelerini destekler)|Evet|  
|[list](../mfc/using-clistctrl.md)|[CListCtrl](../mfc/reference/clistctrl-class.md)|Metin simgelerle görüntüler penceresi|Evet|  
|Liste kutusu|[CListBox](../mfc/reference/clistbox-class.md)|Dizeleri listesini içeren kutusu|Hayır|  
|[Ay takvim](../mfc/using-cmonthcalctrl.md)|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|Tarih bilgileri görüntüleyen denetimi|Evet|  
|[ilerleme durumu](../mfc/using-cprogressctrl.md)|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Uzun bir işlemin ilerlemesini gösterir penceresi|Evet|  
|[Rebar](../mfc/using-crebarctrl.md)|[CRebarCtrl](../mfc/reference/crebarctrl-class.md)|Ek alt windows denetimleri biçiminde içerebilir araç çubuğu|Evet|  
|[zengin düzenleme](../mfc/using-cricheditctrl.md)|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|Hangi kullanıcı penceresinde karakter ve paragraf biçimlendirmesini düzenleyebilirsiniz (bkz [zengin düzenleme denetimleri ilgili sınıflar](../mfc/classes-related-to-rich-edit-controls.md))|Evet|  
|kaydırma çubuğu|[CScrollBar](../mfc/reference/cscrollbar-class.md)|Bir iletişim kutusu (değil, bir pencere) içindeki bir denetim olarak kullanılan kaydırma çubuğu|Hayır|  
|[Kaydırıcı](../mfc/using-csliderctrl.md)|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|İsteğe bağlı bir kaydırıcı denetimi içeren pencere onay işaretleri|Evet|  
|[değer değiştirme düğmesi](../mfc/using-cspinbuttonctrl.md)|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Ok düğmelerini kullanıcı çifti için artışı tıklatın veya bir değer azaltma|Evet|  
|statik metin|[CStatic](../mfc/reference/cstatic-class.md)|Diğer denetimleri etiketlemek için metin|Hayır|  
|[Durum çubuğu](../mfc/using-cstatusbarctrl.md)|[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)|MFC sınıfı benzer durumu bilgilerini görüntüleme penceresi`CStatusBar`|Evet|  
|[sekmesi](../mfc/using-ctabctrl.md)|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Bir dizüstü bilgisayarın Bölücü benzer; kullanılan "sekme iletişim kutuları" veya özellik sayfaları|Evet|  
|[araç çubuğu](../mfc/using-ctoolbarctrl.md)|[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)|Komut oluşturma penceresiyle düğmeleri, benzer şekilde MFC sınıfı`CToolBar`|Evet|  
|[Araç İpucu](../mfc/using-ctooltipctrl.md)|[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)|Araç çubuğu düğmesi veya başka bir araç amacını açıklayan küçük açılır penceresi|Evet|  
|[Ağaç](../mfc/using-ctreectrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Hiyerarşik öğelerin listesini görüntüleyen penceresi|Evet|  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   Tek bir denetim: tabloya bakın [Windows ortak denetimleri ve MFC sınıfları](#_core_windows_common_controls_and_mfc_classes) tüm denetimler bağlantılar için bu konudaki  
  
-   [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)  
  
-   [Denetim eklemek için iletişim kutusu düzenleyicisini kullanma](../mfc/using-the-dialog-editor-to-add-controls.md)  
  
-   [Bir iletişim kutusu için el ile denetim ekleme](../mfc/adding-controls-by-hand.md)  
  
-   [MFC denetim sınıflardan türetme denetim sınıfları](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Alt öğe pencerelerini ortak denetimleri kullanma](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Ortak Denetimler bildirimleri](../mfc/receiving-notification-from-common-controls.md)  
  
-   [Ortak Denetimler Ekle iletişim kutusu için](../mfc/using-common-controls-in-a-dialog-box.md).  
  
-   [Standart Windows denetimden denetim türetilen](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Tür güvenliği ile erişim iletişim kutusu denetimleri](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [Ortak denetimlerden bildirim iletilerini alma](../mfc/receiving-notification-from-common-controls.md)  
  
-   [Örnekler](../mfc/common-control-sample-list.md)  
  
 Windows ortak denetimleri Windows SDK hakkında daha fazla bilgi için bkz: [ortak denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

