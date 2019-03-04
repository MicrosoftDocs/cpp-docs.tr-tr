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
ms.openlocfilehash: 8c60469747c24b4c295348a14cb569c4118c76d9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260484"
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

   [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

1. Aşağıdaki kodu ekleyin `OnViewTest` işlevi uygulamak için:

   [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]

### <a name="to-display-a-modeless-dialog-box"></a>Kalıcı olmayan iletişim kutusunu görüntülemek için

1. View sınıfı (CDisplayDialogView) 4. adımda seçin dışında bir kalıcı iletişim kutusunu görüntülemek için ilk dört adımları uygulayın.

1. DisplayDialogView.h düzenleyin:

   - Birinci sınıf bildiriminden önceki iletişim kutusu sınıfı bildirin:

         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]

   - İletişim kutusu için bir işaretçi öznitelikleri ortak bölümüne sonra bildirin:

         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]

1. DisplayDialogView.cpp düzenleyin:

   - Var olan dahil sonra deyimleri aşağıdaki deyimi ekleyin:

         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

   - Aşağıdaki kod oluşturucuyu ekleyin:

         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]

   - Yok edici için aşağıdaki kodu ekleyin:

         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]

   - Aşağıdaki kodu ekleyin `OnViewTest` işlevi uygulamak için:

         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Kalıcı ve Kalıcı Olmayan İletişim Kutuları](../mfc/modal-and-modeless-dialog-boxes.md)
