---
title: İletişim kutusu denetimleri ve değişken türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6914ab8b5838ee6bc5bb7a74004ed986efe2fcda
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373993"
---
# <a name="dialog-box-controls-and-variable-types"></a>İletişim Kutusu Denetimleri ve Değişken Türleri

Kullanabileceğiniz [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md) MFC kullanılarak oluşturulan bir iletişim kutusu denetimine bir üye değişkeni eklemek için. Türü denetim üye değişkeni Ekle iletişim kutusunda görünen seçenekleri belirler.

MFC'de desteklenen tüm iletişim kutusu denetim türleri aşağıdaki tabloda açıklanmıştır ve [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)ve kullanılabilir türleri ve değerleri.

|Denetim|Denetim türü|Denetim değişkeni türü|Değişken türü değeri|En düşük/en yüksek değerleri (yalnızca değer türü)|
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|
|Animasyon denetimi|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|None; yalnızca denetim|Yok|
|Düğme|DÜĞME|[CButton](../mfc/reference/cbutton-class.md)|None; yalnızca denetim|Yok|
|Onay kutusu|ONAY|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|En düşük değer/en yüksek değeri|
|Birleşik giriş kutusu|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|En fazla karakter|
|Tarih Saat Seçici denetimi|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|En düşük değer/en yüksek değeri|
|Düzenleme kutusu|DÜZENLE|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, long, UINT, DWORD, double, BYTE, kısa, BOOL, float `COleDateTime`, veya **COleCurrency**|En düşük değer/en yüksek değeri; Bazı destek en fazla karakter|
|Kısayol tuşu denetimi|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|None; yalnızca denetim|Yok|
|Liste kutusu|LİSTE KUTUSU|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|En fazla karakter|
|Liste denetimi|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|None; yalnızca denetim|Yok|
|Ay takvim denetimi|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|En düşük değer/en yüksek değeri|
|İlerleme denetimi|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|None; yalnızca denetim|Yok|
|Zengin düzenleme 2 denetimi|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|En fazla karakter|
|Zengin düzenleme denetimi|RICHEDIT|`CRichEditCtrl`|`CString`|En fazla karakter|
|(Dikey veya yatay kaydırma çubuğu|KAYDIRMA ÇUBUĞU|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|En düşük değer/en yüksek değeri|
|Kaydırıcı denetimi|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|En düşük değer/en yüksek değeri|
|Döndürme denetimi|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|None; yalnızca denetim|Yok|
|Sekme denetimi|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|None; yalnızca denetim|Yok|
|Ağaç denetimi|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|None; yalnızca denetim|Yok|

## <a name="see-also"></a>Ayrıca Bkz.

[Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)