---
title: Tarih ve Saat Seçici Denetimini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: de9baf63577d163b82da1c5977a6ccba6539c73a
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907598"
---
# <a name="creating-the-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetimini Oluşturma

Tarih ve saat seçici denetiminin nasıl oluşturulduğu, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>CDateTimeCtrl ' i doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde, iletişim kutusu şablonu kaynağınız için bir tarih ve saat seçici denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Tarih ve saat seçici denetiminin Özellikler iletişim kutusunu kullanarak gereken stilleri belirtin.

1. Denetim özelliğiyle [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı 'nı](../ide/adding-a-member-variable-visual-cpp.md) kullanın. Bu üyeyi, üye işlevlerini çağırmak `CDateTimeCtrl` için kullanabilirsiniz.

1. İşlemek için gereken tarih saat Seçici denetim [bildirim](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) iletileri için İletişim sınıfındaki işleyici işlevlerini eşlemek Için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)' da `CDateTimeCtrl` nesne için ek stiller ayarlayın.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CDateTimeCtrl kullanma

1. Görünümü veya pencere sınıfında denetimi bildirin.

1. Denetimin üye [Oluştur](../mfc/reference/ctabctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
