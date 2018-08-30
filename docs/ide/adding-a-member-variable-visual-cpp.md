---
title: Üye değişkeni (Visual C++) ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.member.variable
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d20611d2cc5e4b391e2dafdef614dd5173d32ef7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207304"
---
# <a name="adding-a-member-variable--visual-c"></a>Üye Değişkeni Ekleme (Visual C++)
Sınıf görünümü kullanarak bir sınıfa üye değişkeni ekleyebilirsiniz. Üye değişkenleri için ya da olabilir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md), veya genel olabilir. Veri üye değişkeni Sihirbazı'nı, ilgili bilgileri almak ve uygun yerlerde, kaynak dosyalarında öğe eklemek için kullanmak için özel olarak tasarlanmıştır. Bir üye değişkeninin ekleyebilirsiniz [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) içinde [kaynak görünümü](../windows/resource-view-window.md), veya [sınıf görünümü](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
> [!NOTE]
>  Tasarlarken ve iletişim kutusu uygulama, onu daha verimli bir iletişim kutusunda kullanılacak Düzenleyicisi iletişim kutusu denetimleri eklemek için bulabilirsiniz ve ardından Denetim üyesi değişkenleri uygulamak için.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>Üye değişkeni Ekleme Sihirbazı'nı kullanarak kaynak görünümünde bir iletişim denetimi için bir üye değişkeni eklemek için  
  
1.  Kaynak Görünümü'nde, proje ve proje iletişim kutuları listesini görüntülemek için iletişim düğümlerini genişletin.  
  
2.  İletişim kutusu Düzenleyicisi'nde açmak için üye değişkeni eklemek istediğiniz iletişim kutusu çift tıklayın.  
  
3.  İletişim kutusu Düzenleyicisi'nde görüntülenen iletişim kutusunda, bir üye değişkeni eklemek istediğiniz denetime sağ tıklayın.  
  
4.  Kısayol menüsünde **değişken Ekle** görüntülenecek [ekleme üye değişkeni Sihirbazı](../ide/add-member-variable-wizard.md).  
  
    > [!NOTE]
    >  Varsayılan değer zaten sağlanan **denetim kimliği**.  
  
5.  Uygun Sihirbazı kutularındaki bilgileri sağlayın. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.  
  
6.  Tıklayın **son** tanım ve uygulamayı kod projeye ekleyin ve sihirbazı kapatın.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>Sınıf Görünümü üye değişkeni Ekleme Sihirbazı'nı kullanarak bir üye değişkeni eklemek için  
  
1.  İçinde [sınıf görünümü](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925), projede sınıflarını görüntülemek için proje düğümünü genişletin.  
  
2.  Bir değişkeni eklemek istediğiniz sınıf sağ tıklayın.  
  
3.  Kısayol menüsünde **Ekle**ve ardından **değişken Ekle** ekleme üye değişkeni Sihirbazı görüntülenecek.  
  
4.  Uygun Sihirbazı kutularındaki bilgileri sağlayın. Bkz: [ekleme üye değişkeni Sihirbazı](../ide/add-member-variable-wizard.md) Ayrıntılar için.  
  
5.  Tıklayın **son** tanım ve uygulamayı kod projeye ekleyin ve sihirbazı kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)