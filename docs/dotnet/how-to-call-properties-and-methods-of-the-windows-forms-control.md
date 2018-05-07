---
title: 'Nasıl yapılır: Çağrı özellikleri ve yöntemleri Windows Forms denetimi | Microsoft Docs'
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
ms.openlocfilehash: 206c7bc89ce2bbc48beb1d95f3929ea4694fce20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>Nasıl yapılır: Windows Forms Denetiminin Çağrı Özellikleri ve Yöntemleri
Çünkü [CWinFormsView::GetControl](../mfc/reference/cwinformsview-class.md#getcontrol) gösteren bir işaretçi döndürür <xref:System.Windows.Forms.Control?displayProperty=fullName>ve işaretçisi değil `WindowsControlLibrary1::UserControl1`, kullanıcı denetimi türü üyesi eklemek ve bunu başlatmak için önerilir [IView::OnInitialUpdate ](../mfc/reference/iview-interface.md#oninitialupdate). Kullanarak yöntemleri ve özellikleri çağırabilirsiniz artık `m_ViewControl`.  
  
 Bu konuda daha önce tamamlandı varsayılır [nasıl yapılır: bir iletişim kutusunda kullanıcı denetimi ve konak oluşturma](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) ve [nasıl yapılır: kullanıcı denetimi ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>MFC konak uygulaması oluşturmak için  
  
1.  Oluşturduğunuz MFC uygulamasında açmak [nasıl yapılır: kullanıcı denetimi ve konak MDI görünümü oluşturma](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
2.  Genel geçersiz kılmalar bölümüne aşağıdaki satırı ekleyin `CMFC02View` sınıf bildiriminin MFC02View.h'taki.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  Bir geçersiz kılma için OnInitialUpdate ekleyin.  
  
     Görüntü **özellikleri** penceresi (F4). İçinde **sınıf görünümü** (CTRL + SHIFT + C), CMFC02View sınıfını seçin. İçinde **özellikleri** penceresinde, geçersiz kılmalar için simgeyi seçin. OnInitialUpdate'e kadar aşağı inin listesi. Liste ve Seç açılan tıklatıldığında \<Ekle >. MFC02View.cpp'de. OnInitialUpdate işlevinin gövdesini aşağıdaki gibi olduğundan emin olun:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  Oluşturun ve projeyi çalıştırın.  
  
     Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat hata ayıklama olmadan**.  
  
     Metin kutusunun başlatıldığına dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Görünümü Olarak Windows Forms Kullanıcı Denetimi Barındırma](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)