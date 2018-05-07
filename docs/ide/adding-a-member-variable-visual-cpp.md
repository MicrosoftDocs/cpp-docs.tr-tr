---
title: (Visual C++) üye değişkeni ekleme | Microsoft Docs
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
ms.openlocfilehash: fa2a8ef8f7bcdc2d90893acdad98705c9588a5d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-member-variable--visual-c"></a>Üye Değişkeni Ekleme (Visual C++)
Sınıf görünümü kullanarak bir sınıf bir üye değişkenine ekleyebilirsiniz. Üye değişkenleri için ya da olabilir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md), veya genel olabilir. Veri üye değişkeni Sihirbazı'nı ilgili bilgileri geçirmek ve uygun konumlara kaynak dosyalarınızda öğe eklemek için kullanmak üzere özel olarak tasarlanmıştır. Üye değişkeninden ekleyebilirsiniz [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) içinde [kaynak görünümü](../windows/resource-view-window.md), veya [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
> [!NOTE]
>  Tasarlarken ve bir iletişim kutusu uygulama, bu iletişim kutusunu kullanmak için daha verimli Düzenleyicisi iletişim kutusu denetimleri eklemek için bulabilirsiniz ve denetimleri üye değişkenleri uygulamak için.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>Üye değişkeni Ekleme Sihirbazı'nı kullanarak kaynak görünümünde bir iletişim kutusu denetimi için bir üye değişkeni eklemek için  
  
1.  Kaynak Görünümü'nde, proje düğümüne ve projenin iletişim kutuları listesini görüntülemek için iletişim düğümünü genişletin.  
  
2.  İletişim kutusu düzenleyicisinde açmak için üye değişkeni eklemek istediğiniz iletişim kutusuna çift tıklayın.  
  
3.  İletişim kutusu Düzenleyicisi'nde görüntülenen iletişim kutusunda üye değişkeni eklemek istediğiniz denetimi sağ tıklatın.  
  
4.  Kısayol menüsünde **değişken Ekle** görüntülemek için [üye değişkeni ekleme](../ide/add-member-variable-wizard.md).  
  
    > [!NOTE]
    >  Varsayılan değer zaten sağlanan **denetim kimliği**.  
  
5.  Uygun Sihirbazı kutularındaki bilgileri sağlayın. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.  
  
6.  Tıklatın **son** tanımı ve uygulama kodu projeye ekleyin ve sihirbazı kapatın.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>Sınıf üye değişkeni Ekleme Sihirbazı'nı kullanarak görünümünden bir üye değişkeni eklemek için  
  
1.  İçinde [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), projede sınıflarını görüntülemek için proje düğümünü genişletin.  
  
2.  Bir değişkeni eklemek istediğiniz sınıfı sağ tıklatın.  
  
3.  Kısayol menüsünde **Ekle**ve ardından **değişken Ekle** ekleme üye değişkeni Sihirbazı'nı görüntülemek için.  
  
4.  Uygun Sihirbazı kutularındaki bilgileri sağlayın. Bkz: [üye değişkeni ekleme](../ide/add-member-variable-wizard.md) Ayrıntılar için.  
  
5.  Tıklatın **son** tanımı ve uygulama kodu projeye ekleyin ve sihirbazı kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)