---
title: "İletişim kutusu denetimleri için olay işleyicileri ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, adding event handlers to controls
- controls [C++], event handlers
- dialog box controls, events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afe50d56d6b96cc4bc0b871f72c27feb0a750e89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme
Olay işleyicileri oluştururken, sınıf ile ilişkili olan proje iletişim kutuları için bazı kısayollarından sürebilir. Varsayılan Denetim bildirim olayı veya herhangi bir geçerli Windows iletisi için bir işleyici kolayca oluşturabilirsiniz.  
  
#### <a name="to-create-a-handler-for-the-default-control-notification-event"></a>Varsayılan Denetim bildirim olayı için bir işleyici oluşturmak için  
  
1.  Denetimi çift tıklatın. Metin Düzenleyicisi'ni açar.  
  
2.  Denetim bildirimi işleyici kodu Metin Düzenleyicisi'nde ekleyin.  
  
#### <a name="to-create-a-handler-for-any-applicable-windows-message"></a>Geçerli Windows iletiler için bir işleyici oluşturmak için  
  
1.  Bildirim olayını işlemek istediğiniz denetimi'ı tıklatın.  
  
2.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), tıklatın **ControlEvents'i** denetimle ilişkili ortak Windows olayları listesini görüntülemek için düğmesi. Örneğin, standart **Tamam** düğmesini **hakkında** iletişim kutusu aşağıdaki bildirim olayları listeler:  
  
 **BN_CLICKED**  
  
 **BN_DOUBLECLICKED**  
  
 **BN_KILLFOCUS**  
  
 **BN_SETFOCUS**  
  
    > [!NOTE]
    >  Alternatif olarak, iletişim kutusunu işaretleyin ve ' **ControlEvents'i** tüm denetimler için yaygın Windows olaylar listesi iletişim kutusunda görüntülenecek düğmesi.  
  
3.  İçinde **özellikleri** penceresinde, işlenecek olay yanındaki sağ sütun tıklayın ve ardından önerilen bildirim olay adı seçin (örneğin, **OnBnClickedOK** tanıtıcıları **BN_CLICKED** ).  
  
    > [!NOTE]
    >  Alternatif olarak, varsayılan olay işleyicisi adı seçmek yerine tercih ettiğiniz bir olay işleyicisi adı sağlayabilir.  
  
     Olay seçtikten sonra Visual Studio Metin Düzenleyicisi'ni açar ve olay işleyicinin kodunu görüntüler. Örneğin, aşağıdaki kodu için varsayılan eklenir **OnBnClickedOK**:  
  
 ```  
    void CAboutDlg::OnBnClickedOk(void)  
 { *// TODO: Add your control notification handler code here  
 }  
 ```  
  
 Olay işleyicisi bir sınıfa dışındaki bir iletişim kutusu uygulama eklemek istiyorsanız kullanın [olay işleyici Sihirbazı](../ide/event-handler-wizard.md). Daha fazla bilgi için bkz: [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Varsayılan denetim olayları](../windows/default-control-events.md)   
 [İletişim kutusu denetimleri için üye değişkenleri tanımlama](../windows/defining-member-variables-for-dialog-controls.md)   
 [İletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md)   
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)

