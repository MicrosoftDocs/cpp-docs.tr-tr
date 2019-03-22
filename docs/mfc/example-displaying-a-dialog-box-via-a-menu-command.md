---
title: 'Örnek: Bir iletişim kutusunu menü komutu ile görüntüleme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 1e730125e47609f0bf87814b32962336cb752b04
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328278"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Örnek: Bir iletişim kutusunu menü komutu ile görüntüleme

Bu konu, yordamları içerir:

- Bir menü komutu ile kalıcı bir iletişim kutusu görüntülenir.

- Bir menü komutu aracılığıyla modsuz iletişim kutusu görüntülenir.

Her iki örnek yordamları için MFC uygulamaları ve ile oluşturduğunuz bir uygulamada çalışır [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md).

Adları ve değerleri aşağıdaki yordamları kullanın:

|Öğe|Ad veya değer|
|----------|-------------------|
|Uygulama|DisplayDialog|
|Menü komutu|Görünüm menüsünde komut sınayın. Komut Kimliği ID_VIEW_TEST =|
|İletişim kutusu|Test iletişim kutusu; Sınıf CTestDialog; = Üst bilgi dosyası TestDialog.h; = Değişken testdlg, ptestdlg =|
|Komut işleyicisi|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>Kalıcı bir iletişim kutusu görüntülemek için

1. Menü komutu oluşturmak; bkz: [oluşturma menü veya menü öğelerini](../windows/creating-a-menu.md).

1. İletişim kutusu oluşturma bkz: [iletişim kutusu Düzenleyicisi başlatılıyor](../windows/creating-a-new-dialog-box.md).

1. İletişim kutusu için bir sınıf ekleyin. Bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md) daha fazla bilgi için.

1. İçinde **sınıf görünümü**, belge sınıfı (CDisplayDialogDoc) seçin. İçinde **özellikleri** penceresinde tıklayın **olayları** düğmesi. Menü komutunu (ID_VIEW_TEST) sol bölmesinde Kimliği'ne çift tıklayın **özellikleri** penceresi ve select **komut**. Sağ bölmede aşağı oka tıklayıp  **\<Ekle > OnViewTest**.

   Uygulama sınıfı (CDisplayDialogApp), bunun yerine bir MDI uygulaması ana bilgisayar için menü komutunu eklediyseniz, seçin.

1. Şunlar CDisplayDialogDoc.cpp (veya CDisplayDialogApp.cpp) ifadesine ekleyin varolan dahil sonra deyimleri:

   ```cpp
   #include "TestDialog.h"
   ```

1. Aşağıdaki kodu ekleyin `OnViewTest` işlevi uygulamak için:

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal();  
   ```

### <a name="to-display-a-modeless-dialog-box"></a>Kalıcı olmayan iletişim kutusunu görüntülemek için

1. View sınıfı (CDisplayDialogView) 4. adımda seçin dışında bir kalıcı iletişim kutusunu görüntülemek için ilk dört adımları uygulayın.

1. DisplayDialogView.h düzenleyin:

   - Birinci sınıf bildiriminden önceki iletişim kutusu sınıfı bildirin:

   ```cpp
   class CTestDialog;
   ```

   - İletişim kutusu için bir işaretçi öznitelikleri ortak bölümüne sonra bildirin:

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. DisplayDialogView.cpp düzenleyin:

   - Var olan dahil sonra deyimleri aşağıdaki deyimi ekleyin:

   ```cpp
   #include "TestDialog.h"
   ```

   - Aşağıdaki kod oluşturucuyu ekleyin:

   ```cpp
   m_pTestDlg = NULL;
   ```

   - Yok edici için aşağıdaki kodu ekleyin:

   ```cpp
   delete m_pTestDlg;
   ```

   - Aşağıdaki kodu ekleyin `OnViewTest` işlevi uygulamak için:

   ```cpp
   if (NULL == m_pTestDlg)
   {
      m_pTestDlg = new CTestDialog(this);
      m_pTestDlg->Create(CTestDialog::IDD, this);
   }
   m_pTestDlg->ShowWindow(SW_SHOW); 
   ```

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Kalıcı ve Kalıcı Olmayan İletişim Kutuları](../mfc/modal-and-modeless-dialog-boxes.md)
