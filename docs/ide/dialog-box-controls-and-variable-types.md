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
ms.openlocfilehash: f2fbae37072f50898181334a9059a7dc9c6a83a9
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33335071"
---
# <a name="dialog-box-controls-and-variable-types"></a>İletişim Kutusu Denetimleri ve Değişken Türleri
Kullanabileceğiniz [üye değişkeni Ekleme Sihirbazı'nı](../ide/add-member-variable-wizard.md) MFC kullanılarak oluşturulan bir iletişim kutusu denetimi için üye değişkeni eklemek için. Üye değişkeni ekleme denetim türü iletişim kutusunda görüntülenen seçenekleri belirler.  
  
 MFC'de desteklenen tüm iletişim kutusu denetimi türleri aşağıdaki tabloda açıklanmıştır ve [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)ve kullanılabilir türleri ve değerleri.  
  
|Denetim|Denetim türü|Denetim değişken türü|Değer değişken türü|Min/max değerleri (yalnızca değer türü)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|Animasyon denetimi|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|Yok; yalnızca denetim|Yok|  
|Düğme|DÜĞMESİ|[CButton](../mfc/reference/cbutton-class.md)|Yok; yalnızca denetim|Yok|  
|Onay kutusu|ONAY|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|En düşük değer/Max değeri|  
|Birleşik giriş kutusu|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|En fazla karakter|  
|Tarih Saat Seçici denetimi|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|En düşük değer/max değeri|  
|Düzenleme kutusu|DÜZENLEME|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, uzun DWORD, double, bayt, kısa, BOOL, float `COleDateTime`, veya **COleCurrency**|En düşük değer/max değeri; Bazı destek en fazla karakter|  
|Kısayol tuşu denetimi|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|Yok; yalnızca denetim|Yok|  
|Liste kutusu|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|En fazla karakter|  
|Liste denetimi|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|Yok; yalnızca denetim|Yok|  
|Ay takvim denetleme|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|En düşük değer/max değeri|  
|İlerleme denetimi|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|Yok; yalnızca denetim|Yok|  
|Zengin düzenleme 2 denetimi|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|En fazla karakter|  
|Zengin düzenleme denetimi|RICHEDIT|`CRichEditCtrl`|`CString`|En fazla karakter|  
|(Dikey veya yatay kaydırma çubuğu|KAYDIRMA ÇUBUĞU|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|En düşük değer/max değeri|  
|Kaydırıcı denetimi|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|En düşük değer/max değeri|  
|Döndürme denetimi|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|Yok; yalnızca denetim|Yok|  
|Sekme denetimi|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|Yok; yalnızca denetim|Yok|  
|Ağaç denetimi|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|Yok; yalnızca denetim|Yok|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)