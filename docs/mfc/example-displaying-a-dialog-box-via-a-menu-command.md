---
title: 'Örnek: bir iletişim kutusunu menü komutu ile görüntüleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20d355215388861a7bc2586c2c253cd551124809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Örnek: Bir İletişim Kutusunu Menü Komutu ile Görüntüleme
Bu konudaki yordamları içerir:  
  
-   Kalıcı iletişim kutusunu menü komutu ile görüntüleyin.  
  
-   Kalıcı olmayan iletişim kutusunu menü komutu ile görüntüleyin.  
  
 Her iki örnek yordamları MFC uygulamaları için ve bir uygulama oluşturma ile çalışır [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md).  
  
 Aşağıdaki adları ve değerleri yordamları kullanın:  
  
|Öğe|Ad veya değer|  
|----------|-------------------|  
|Uygulama|DisplayDialog|  
|Menü komutu|Görünüm menüsü komutunda test; Komut Kimliği ID_VIEW_TEST =|  
|İletişim kutusu|Test iletişim kutusu; Sınıf CTestDialog; = Üstbilgi dosyası TestDialog.h; = Değişken testdlg, ptestdlg =|  
|Komut işleyici|OnViewTest|  
  
### <a name="to-display-a-modal-dialog-box"></a>Kalıcı iletişim kutusunu görüntülemek için  
  
1.  Menü komutu oluşturun; bkz: [oluşturma menü veya menü öğeleri](../windows/creating-a-menu.md).  
  
2.  Oluştur iletişim kutusu; bkz: [iletişim kutusu Düzenleyicisi başlangıç](../windows/creating-a-new-dialog-box.md).  
  
3.  İletişim kutusu için bir sınıf ekleyin. Bkz: [sınıf ekleme](../ide/adding-a-class-visual-cpp.md) daha fazla bilgi için.  
  
4.  İçinde **sınıf görünümü**, belge sınıfı (CDisplayDialogDoc) seçin. İçinde **özellikleri** penceresinde tıklatın **olayları** düğmesi. Sol bölmesinde menü komutu (ID_VIEW_TEST) Kimliğini çift **özellikleri** penceresini açın ve Seç **komutu**. Sağ bölmede, aşağı oka tıklayın ve  **\<Ekle > OnViewTest**.  
  
     Menü komutu ile bir MDI uygulama anabilgisayar eklediyseniz, bunun yerine uygulama sınıfı (CDisplayDialogApp) seçin.  
  
5.  Şunlar deyimi CDisplayDialogDoc.cpp (veya CDisplayDialogApp.cpp) eklemek varolan dahil sonra deyimleri:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  Aşağıdaki kodu ekleyin `OnViewTest` işlevi uygulamak için:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### <a name="to-display-a-modeless-dialog-box"></a>Kalıcı olmayan iletişim kutusunu görüntülemek için  
  
1.  View sınıfı (CDisplayDialogView) 4. adımda seçin dışında bir modal iletişim kutusu görüntülemek için ilk dört adımları uygulayın.  
  
2.  DisplayDialogView.h düzenleyin:  
  
    -   Birinci sınıf bildiriminden önceki iletişim kutusu sınıfı bildirin:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   İletişim kutusu için bir işaretçi öznitelikleri ortak bölümünden sonra bildirin:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  DisplayDialogView.cpp düzenleyin:  
  
    -   Varolan dahil sonra deyimleri deyimi şunlardır ekleyin:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   Oluşturucuya aşağıdaki kodu ekleyin:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   Yıkıcı için aşağıdaki kodu ekleyin:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   Aşağıdaki kodu ekleyin `OnViewTest` işlevi uygulamak için:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 Ayrıca, aşağıdaki Bilgi Bankası makalesine bakın:  
  
-   Q251059: Nasıl yapılır: kendi MFC iletişim kutusu için pencere sınıfı ad  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [Kalıcı ve Kalıcı Olmayan İletişim Kutuları](../mfc/modal-and-modeless-dialog-boxes.md)

