---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Windows Forms denetimin özelliklerini ve yöntemlerini çağırma'
title: 'Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
ms.openlocfilehash: a797084a28eefec27699814a09c8521da7460bc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268411"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri

[CWinFormsView:: GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) <xref:System.Windows.Forms.Control?displayProperty=fullName> , işaretçisine değil, için bir işaretçi döndürdüğünden `WindowsControlLibrary1::UserControl1` , Kullanıcı denetim türünün bir üyesini eklemek ve [IView:: OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate)içinde başlatmak önerilir. Artık kullanarak yöntemleri ve özellikleri çağırabilirsiniz `m_ViewControl` .

Bu konu başlığı altında [, bir Iletişim kutusunda Kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ve [nasıl yapılır: Kullanıcı denetımı ve Konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)hakkında daha önceden tamamladığınız varsayılmaktadır.

### <a name="to-create-the-mfc-host-application"></a>MFC ana bilgisayar uygulaması oluşturmak için

1. [Nasıl yapılır: Kullanıcı denetimi ve Konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)bölümünde oluşturduğunuz mfc uygulamasını açın.

1. Aşağıdaki satırı, `CMFC02View` MFC02View. h içindeki sınıf bildiriminin genel geçersiz kılmalar bölümüne ekleyin.

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. OnInitialUpdate için bir geçersiz kılma ekleyin.

   **Özellikler** penceresini (F4) görüntüleyin. **Sınıf görünümü** (CTRL + SHIFT + C) içinde CMFC02View Class ' ı seçin. **Özellikler** penceresinde, geçersiz kılmalar simgesini seçin. Listenin OnInitialUpdate 'e indirgenme. Açılan listeye tıklayın ve öğesini seçin \<Add> . MFC02View. cpp içinde. OnInitialUpdate işlevinin gövdesinin aşağıdaki gibi olduğundan emin olun:

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. Projeyi derleyin ve çalıştırın.

   **Yapı** menüsünde **Yapı Çözümü**’ne tıklayın.

   **Hata Ayıkla** menüsünde, **hata ayıklama olmadan Başlat**' a tıklayın.

   Metin kutusunun başlatıldığına dikkat edin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
