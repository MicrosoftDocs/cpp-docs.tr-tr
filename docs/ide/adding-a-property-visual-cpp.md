---
title: (Visual C++) özellik ekleme | Microsoft Docs
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
ms.openlocfilehash: 45eda098202fdf9286905bdc967b6aa1d7bd7035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-property-visual-c"></a>Özellik Ekleme (Visual C++)
Kullanabileceğiniz [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md) projenizdeki bir arabirim için bir yöntem eklemek için.  
  
### <a name="to-add-a-property-to-your-object"></a>Bir özellik için nesneyi eklemek için  
  
1.  İçinde [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), özellik eklemek istediğiniz arabirimi adına sağ tıklayın.  
  
    > [!NOTE]
    >  Proje öznitelikli sürece, bu, kitaplık düğümünün içinde iç içe geçmiş dispinterfaces özellikleri ekleyebilirsiniz.  
  
2.  Kısayol menüsünden tıklatın **Ekle**ve ardından **Özellik Ekle**.  
  
3.  İçinde [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md), özellik oluşturmak için bilgileri girin.  
  
4.  Herhangi bir özellik için arabirimi tanım dili (IDL) ayarlarını belirtin [IDL öznitelikleri](../ide/idl-attributes-add-property-wizard.md) Sihirbazı sayfası.  
  
5.  Tıklatın **son** özelliği eklemek için.  
  
 **Almak** ve `Put` özelliğinin yöntemlerini nerede tanımlanan arabirimi altında sınıf görünümündeki iki simgeler olarak görüntülenir. Özellik bildirimi .idl dosyasındaki görüntülemek için her iki simgesini çift tıklatabilirsiniz.  
  
-   ATL arabirimleri için **almak** ve **Put** işlevleri .cpp dosyasına eklenir ve bu işlevlere başvurular .h dosyasına eklenir.  
  
-   MFC dispinterfaces seçerseniz için **üye değişkeni** uygulama türü bunu uygulayan sınıfa bir yöntem ve bir değişkeni eklenir. Seçerseniz **Get/Set yöntemleri** uygulama türü iki yöntem bunu uygulayan sınıfa eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM arabirimi oluşturma](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM arabirimini düzenleme](../ide/editing-a-com-interface.md)   
 [Bileşen Nesne modeli](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [Arabirim işaretçileri ve arabirimleri](http://msdn.microsoft.com/library/windows/desktop/ms688484)