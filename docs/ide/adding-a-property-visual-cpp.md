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
ms.openlocfilehash: e121cf9738910b105f5bb1933592e67d334f8937
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685332"
---
# <a name="adding-a-property-visual-c"></a>Özellik Ekleme (Visual C++)
Kullanabileceğiniz [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md) projenize bir arabirimde bir yöntemi eklemek için.  
  
### <a name="to-add-a-property-to-your-object"></a>Nesneniz için bir özellik eklemek için  
  
1.  İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), özellik eklemek istediğiniz arabirimin adını sağ tıklayın.  
  
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