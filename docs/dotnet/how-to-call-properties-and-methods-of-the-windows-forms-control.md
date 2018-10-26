---
title: 'Nasıl yapılır: denetiminin çağrı özellikleri ve yöntemleri Windows Forms | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 71e42f7d7a60478ec9344a44e8e86463e5845500
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061579"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri

Çünkü [CWinFormsView::GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) bir işaretçi döndürür <xref:System.Windows.Forms.Control?displayProperty=fullName>ve işaretçisi değil `WindowsControlLibrary1::UserControl1`, kullanıcı denetimi türünün üyesi ekleyip bunu başlatabilir önerilir [IView::OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). Yöntemleri ve özellikleri kullanarak çağırabilirsiniz artık `m_ViewControl`.

Bu konuda daha önce bitirdiğinizi [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ve [nasıl yapılır: kullanıcı Denetim ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için

1. Oluşturduğunuz MFC uygulamasını açınız [nasıl yapılır: kullanıcı Denetim ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Genel geçersiz kılmaları kısmına aşağıdaki satırı ekleyin `CMFC02View` MFC02View.h bildiriminde sınıfı.

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. Bir geçersiz kılma için OnInitialUpdate ekleyin.

   Görüntü **özellikleri** penceresini (F4). İçinde **sınıf görünümü** (CTRL + SHIFT + C) CMFC02View sınıfını seçin. İçinde **özellikleri** penceresinde geçersiz kılmalar için simgeyi seçin. Listedeki OnInitialUpdate OnInitialUpdate'e kadar. Tıklayın ve açılan listesinden \<Ekle >. MFC02View.cpp içinde. OnInitialUpdate işlevinin gövdesi şu şekilde olduğundan emin olun:

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. Derleme ve projeyi çalıştırın.

   Üzerinde **derleme** menüsünde tıklatın **Çözümü Derle**.

   Üzerinde **hata ayıklama** menüsünü tıklatın **hata ayıklama olmadan Başlat**.

   Metin kutusu başlatıldığına dikkat edin.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)