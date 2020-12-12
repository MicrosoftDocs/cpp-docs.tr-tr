---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Yerel C++ Sınıflarından Windows Forms olayları havuzu oluşturma'
title: 'Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: 223590849f114bfe02b030a0639f160b8fc1c321
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286364"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları

Yerel C++ sınıflarını, Windows Forms denetimlerinden çıkarılan yönetilen olaylardan veya MFC makro Haritası biçimindeki diğer formlardan geri çağırmaları alacak şekilde etkinleştirebilirsiniz. Görünümler ve iletişim kutularındaki olayları açmak, denetimler için aynı görevi yapmaya benzerdir.

Bunu yapmanız için gerekenler:

- `OnClick` [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)kullanarak denetime bir olay işleyicisi ekleyin.

- [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)ve [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)kullanarak bir temsilci haritası oluşturun.

Bu örnek, [nasıl yapılır: Windows Forms Ile DDX/DDV veri bağlamayı yapma](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)bölümünde yaptığınız işi sürdürür.

Şimdi, MFC denetiminizi ( `m_MyControl` ) `OnClick` yönetilen olay için çağrılan bir yönetilen olay işleyici temsilcisiyle ilişkilendirirsiniz <xref:System.Windows.Forms.Control.Click> .

### <a name="to-attach-the-onclick-event-handler"></a>OnClick olay işleyicisini eklemek için:

1. BOOL CMFC01Dlg:: OnInitDialog uygulamasına aşağıdaki kodu ekleyin:

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. Aşağıdaki kodu, Class CMFC01Dlg: public CDialog bildiriminin bildiriminde bulunan genel bölümüne ekleyin.

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. Son olarak, için uygulamasını `OnClick` CMFC01Dlg. cpp öğesine ekleyin:

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
