---
title: 'Nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuzu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2dd3778dad837ffe23d17b58b4e579844dc71f40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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