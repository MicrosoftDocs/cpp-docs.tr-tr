---
title: (Visual C++) üye değişkeni ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.member.variable
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
ms.openlocfilehash: 3c7f64fae00e489da7c71bcfe5731db72e1afdf7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595786"
---
# <a name="adding-a-member-variable--visual-c"></a>Üye Değişkeni Ekleme (Visual C++)

Sınıf görünümü kullanarak bir sınıfa üye değişkeni ekleyebilirsiniz. Üye değişkenleri için ya da olabilir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md), veya genel olabilir. Veri üye değişkeni Sihirbazı'nı, ilgili bilgileri almak ve uygun yerlerde, kaynak dosyalarında öğe eklemek için kullanmak için özel olarak tasarlanmıştır. Bir üye değişkeninin ekleyebilirsiniz [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md) içinde [kaynak görünümü](../windows/resource-view-window.md), veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code).

> [!NOTE]
>  Tasarlarken ve iletişim kutusu uygulama, onu daha verimli bir iletişim kutusunda kullanılacak Düzenleyicisi iletişim kutusu denetimleri eklemek için bulabilirsiniz ve ardından Denetim üyesi değişkenleri uygulamak için.

### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>Üye değişkeni Ekleme Sihirbazı'nı kullanarak kaynak görünümünde bir iletişim denetimi için bir üye değişkeni eklemek için

1. Kaynak Görünümü'nde, proje ve proje iletişim kutuları listesini görüntülemek için iletişim düğümlerini genişletin.

1. İletişim kutusu Düzenleyicisi'nde açmak için üye değişkeni eklemek istediğiniz iletişim kutusu çift tıklayın.

1. İletişim kutusu Düzenleyicisi'nde görüntülenen iletişim kutusunda, bir üye değişkeni eklemek istediğiniz denetime sağ tıklayın.

1. Kısayol menüsünde **değişken Ekle** görüntülenecek [ekleme üye değişkeni Sihirbazı](../ide/add-member-variable-wizard.md).

   > [!NOTE]
   > Varsayılan değer zaten sağlanan **denetim kimliği**.

1. Uygun Sihirbazı kutularındaki bilgileri sağlayın. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.

1. Tıklayın **son** tanım ve uygulamayı kod projeye ekleyin ve sihirbazı kapatın.

### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>Sınıf Görünümü üye değişkeni Ekleme Sihirbazı'nı kullanarak bir üye değişkeni eklemek için

1. İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), projede sınıflarını görüntülemek için proje düğümünü genişletin.

1. Bir değişkeni eklemek istediğiniz sınıf sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **değişken Ekle** ekleme üye değişkeni Sihirbazı görüntülenecek.

1. Uygun Sihirbazı kutularındaki bilgileri sağlayın. Bkz: [ekleme üye değişkeni Sihirbazı](../ide/add-member-variable-wizard.md) Ayrıntılar için.

1. Tıklayın **son** tanım ve uygulamayı kod projeye ekleyin ve sihirbazı kapatın.

## <a name="see-also"></a>Ayrıca Bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)<br>
[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)<br>
[MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)