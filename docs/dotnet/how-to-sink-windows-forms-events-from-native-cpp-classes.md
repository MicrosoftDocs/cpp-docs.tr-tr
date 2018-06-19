---
title: 'Nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuzu | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0fec32bf179424b5ec0164e4511f74eae44f7320
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130431"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları
Windows Forms denetimleri veya MFC makro eşlemesi biçimindeki diğer formlardan yükseltilen yönetilen olaylardan geri aramalar almak için yerel C++ sınıflarını etkinleştirebilirsiniz. Görünümleri ve iletişim kutuları olayları indirme denetimleri için aynı görev yapmaya benzer.  
  
 Bunu yapmak için aktarmanız gerekir:  
  
-   Attach bir `OnClick` denetimini kullanarak için olay işleyicisini [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).  
  
-   Kullanarak temsilci eşleme oluşturun [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), ve [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).  
  
 Bu örnek yaptığınız çalışmaya devam [nasıl yapılır: yapmak DDX/DDV veri bağlaması Windows Forms ile](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
  
 Şimdi, MFC denetiminizi ilişkilendireceğiniz (`m_MyControl`) adlı bir yönetilen olay işleyici temsilcisi ile `OnClick` yönetilen için <xref:System.Windows.Forms.Control.Click> olay.  
  
### <a name="to-attach-the-onclick-event-handler"></a>OnClick olay işleyicisi eklemek için:  
  
1.  BOOL CMFC01Dlg::OnInitDialog uygulamasına aşağıdaki kodu ekleyin:  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  CMFC01Dlg sınıfının bildirimini ortak bölümüne aşağıdaki kodu ekleyin: ortak CDialog.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  Son olarak, uygulama için ekleme `OnClick` olan uygulamayı CMFC01Dlg.cpp'ye için:  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)   
 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)   
 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)