---
title: 'Nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuz'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: d02bcea4efce03c8fb11650d344468236737cfbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387272"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuz

Windows Forms denetimleri veya diğer forms MFC makrosu eşleme biçimi ile oluşturulan yönetilen olaylar geri çağırmaları almak için yerel C++ sınıflarını etkinleştirebilirsiniz. Görünümleri ve iletişim kutuları olayları'nı indirme, denetimler için aynı görev yapmaya benzer.

Bunu yapmak için gerekir:

- Ekleme bir `OnClick` kullanarak denetim için olay işleyicisi [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).

- Temsilci haritasını oluşturmak [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), ve [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).

Bu örnek de yaptığınız çalışmaya devam [nasıl yapılır: Windows Forms ile DDX/DDV veri bağlaması yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).

Şimdi, MFC denetim ilişkilendireceğiniz (`m_MyControl`) adlı bir yönetilen bir olay işleyici temsilcisini ile `OnClick` için yönetilen <xref:System.Windows.Forms.Control.Click> olay.

### <a name="to-attach-the-onclick-event-handler"></a>OnClick olay işleyicisi eklemek için:

1. BOOL CMFC01Dlg::OnInitDialog uygulanması için aşağıdaki kodu ekleyin:

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. Bildirimde CMFC01Dlg sınıfının ortak bölümüne aşağıdaki kodu ekleyin: Genel CDialog.

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. Son olarak, logrequest olayını eklemek `OnClick` için olan uygulamayı CMFC01Dlg.cpp'ye:

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)
