---
title: Özellik ekleme (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00b19fa7166e6edad05d729c5a738a2a827086ae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212801"
---
# <a name="adding-a-property-visual-c"></a>Özellik Ekleme (Visual C++)
Kullanabileceğiniz [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md) projenize bir arabirimde bir yöntemi eklemek için.  
  
### <a name="to-add-a-property-to-your-object"></a>Nesneniz için bir özellik eklemek için  
  
1.  İçinde [sınıf görünümü](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925), özellik eklemek istediğiniz arabirimin adını sağ tıklayın.  
  
    > [!NOTE]
    >  Ayrıca, proje öznitelikli sürece, kitaplık düğümünün içinde iç içe geçmiş görüntüleme özellikleri ekleyebilirsiniz.  
  
2.  Kısayol menüsünden tıklayın **Ekle**ve ardından **Özellik Ekle**.  
  
3.  İçinde [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md), özellik oluşturmak için bilgileri sağlayın.  
  
4.  Bir özellik için arabirim tanımlama dili (IDL) ayarlarını belirtin [IDL öznitelikleri](../ide/idl-attributes-add-property-wizard.md) Sihirbazı sayfası.  
  
5.  Tıklayın **son** özelliği eklemek için.  
  
 **Alma** ve `Put` özelliğinin yöntemlerini, Sınıf Görünümü'nde iki simgeyi altında tanımlanmış olduğu yerlerde arabirimi olarak görüntülenir. Özellik bildiriminde .idl dosyasında görüntülemek için her iki simgesini çift tıklayabilirsiniz.  
  
-   ATL arabirimleri için **alma** ve **Put** işlevleri .cpp dosyasına eklenir ve bu işlevlere yönelik başvurulara .h dosyasına eklenir.  
  
-   MFC görüntüleme seçerseniz için **üye değişkeni** uygulama türü bir yöntem ve bir değişken, kendisini uygulayan sınıfa eklenir. Seçerseniz **Get/Set yöntemleri** uygulama türü iki yöntem bunu uygulayan bir sınıfa eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM arabirimi oluşturma](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM arabirimini düzenleme](../ide/editing-a-com-interface.md)   
 [Bileşen Nesne modeli](/windows/desktop/com/the-component-object-model)   
 [Arabirim işaretçileri ve arabirimler](/windows/desktop/com/interface-pointers-and-interfaces)