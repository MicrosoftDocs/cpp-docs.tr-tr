---
title: İletişim kutusu denetimleri için olay işleyicileri ekleme | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, adding event handlers to controls
- controls [C++], event handlers
- dialog box controls, events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb39e502ccc40531e72f761a414e4088de8b147d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121128"
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme

Olay işleyicileri oluştururken, sınıf ile ilişkili olan proje iletişim kutuları için bazı kısayollarından sürebilir. Varsayılan Denetim bildirim olayı veya herhangi bir geçerli Windows iletisi için bir işleyici kolayca oluşturabilirsiniz.

## <a name="to-create-a-handler-for-the-default-control-notification-event"></a>Varsayılan Denetim bildirim olayı için bir işleyici oluşturmak için

1. Denetimi çift tıklatın. Metin Düzenleyicisi'ni açar.

2. Denetim bildirimi işleyici kodu Metin Düzenleyicisi'nde ekleyin.

## <a name="to-create-a-handler-for-any-applicable-windows-message"></a>Geçerli Windows iletiler için bir işleyici oluşturmak için

1. Bildirim olayını işlemek istediğiniz denetimi'ı tıklatın.

2. İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), tıklatın **ControlEvents'i** denetimle ilişkili ortak Windows olayları listesini görüntülemek için düğmesi. Örneğin, standart **Tamam** düğmesini **hakkında** iletişim kutusu aşağıdaki bildirim olayları listeler:

   - **BN_CLICKED**

   - **BN_DOUBLECLICKED**

   - **BN_KILLFOCUS**

   - **BN_SETFOCUS**

    > [!NOTE]
    > Alternatif olarak, iletişim kutusunu işaretleyin ve ' **ControlEvents'i** tüm denetimler için yaygın Windows olaylar listesi iletişim kutusunda görüntülenecek düğmesi.

3. İçinde **özellikleri** penceresinde, işlenecek olay yanındaki sağ sütun tıklayın ve ardından önerilen bildirim olay adı seçin (örneğin, **OnBnClickedOK** tanıtıcıları **BN_CLICKED** ).

    > [!NOTE]
    > Alternatif olarak, varsayılan olay işleyicisi adı seçmek yerine tercih ettiğiniz bir olay işleyicisi adı sağlayabilir.

   Olay seçtikten sonra Visual Studio Metin Düzenleyicisi'ni açar ve olay işleyicinin kodunu görüntüler. Örneğin, aşağıdaki kodu için varsayılan eklenir **OnBnClickedOK**:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

Olay işleyicisi bir sınıfa dışındaki bir iletişim kutusu uygulama eklemek istiyorsanız kullanın [olay işleyici Sihirbazı](../ide/event-handler-wizard.md). Daha fazla bilgi için bkz: [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).

Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).

### <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Varsayılan Denetim Olayları](../windows/default-control-events.md)  
[İletişim Kutusu Denetimleri için Üye Değişkenleri Tanımlama](../windows/defining-member-variables-for-dialog-controls.md)  
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)  
[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)  
[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)  
[Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)  
[Sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)  
[MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)  
