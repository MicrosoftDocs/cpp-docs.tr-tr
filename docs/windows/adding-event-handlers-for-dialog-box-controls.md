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
ms.openlocfilehash: 2dce9b2ce59eb98c59c7a6cf04be52f3d439fdb0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642857"
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme

Olay işleyicileri oluşturduğunuzda, bir sınıf ile ilişkili olan proje iletişim kutuları için bazı kısayollarından alabilir. Varsayılan Denetim bildirim olayı veya herhangi bir geçerli Windows ileti için bir işleyici hızlıca oluşturabilirsiniz.

### <a name="to-create-a-handler-for-the-default-control-notification-event"></a>Varsayılan Denetim bildirimi olay işleyicisi oluşturmak için

1. Denetimi çift tıklatın. **Metin** Düzenleyicisi açılır.

2. Denetim bildirimi işleyicinizin kodunu içinde Ekle **metin** Düzenleyici.

### <a name="to-create-a-handler-for-any-applicable-windows-message"></a>Herhangi bir geçerli Windows ileti işleyicisi oluşturmak için

1. Bildirim olayı işlemek kullanmak istediğiniz denetimi tıklayın.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), tıklayın **ControlEvents'i** denetimle ilişkili ortak Windows olayları listesini görüntülemek için düğme. Örneğin, standart **Tamam** düğmesini **hakkında** iletişim kutusunda, aşağıdaki bildirim olayları listeler:

   - BN_CLICKED

   - BN_DOUBLECLICKED

   - BN_KILLFOCUS

   - BN_SETFOCUS

    > [!NOTE]
    > Alternatif olarak, iletişim kutusunu seçip tıklayın **ControlEvents'i** tüm denetimler için ortak Windows olayları listesi iletişim kutusunda görüntülenecek düğmesi.

3. İçinde **özellikleri** penceresinde işlenecek olay yanındaki sağ sütuna tıklayın ve ardından önerilen bildirim olay adını seçin (örneğin, `OnBnClickedOK` BN_CLICKED işler).

    > [!NOTE]
    > Alternatif olarak, varsayılan olay işleyicisi adı seçmek yerine kendi seçtiğiniz bir olay işleyicisi adı sağlayabilirsiniz.

   Olayı seçtikten sonra Visual Studio açılır **metin düzenleyici** ve olay işleyicinin kodunu görüntüler. Örneğin, aşağıdaki kod için varsayılan eklenir `OnBnClickedOK`:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

Olay işleyicisi bir sınıfa dışındaki bir iletişim kutusu uygulama eklemek istiyorsanız kullanın [olay işleyici Sihirbazı](../ide/event-handler-wizard.md). Daha fazla bilgi için [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler
 Win32

## <a name="see-also"></a>Ayrıca Bkz.
 [Varsayılan Denetim Olayları](../windows/default-control-events.md)  
 [İletişim Kutusu Denetimleri için Üye Değişkenleri Tanımlama](../windows/defining-member-variables-for-dialog-controls.md)  
 [İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)  
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)  
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)  
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)  
 [Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)  
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)  