---
title: Tarih ve Saat Seçici Denetimini Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: 5d753b166454b795932ec8f47b0897829fab9b8e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620465"
---
# <a name="creating-the-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetimini Oluşturma

Tarih ve saat seçici denetiminin nasıl oluşturulduğu, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>CDateTimeCtrl ' i doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde, iletişim kutusu şablonu kaynağınız için bir tarih ve saat seçici denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Tarih ve saat seçici denetiminin Özellikler iletişim kutusunu kullanarak gereken stilleri belirtin.

1. Denetim özelliğiyle [CDateTimeCtrl](reference/cdatetimectrl-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı 'nı](../ide/adding-a-member-variable-visual-cpp.md) kullanın. Bu üyeyi, üye işlevlerini çağırmak için kullanabilirsiniz `CDateTimeCtrl` .

1. İşlemek için gereken tarih saat Seçici denetim [bildirim](processing-notification-messages-in-date-and-time-picker-controls.md) iletileri için İletişim sınıfındaki işleyici işlevlerini eşlemek Için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)' da nesne için ek stiller ayarlayın `CDateTimeCtrl` .

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CDateTimeCtrl kullanma

1. Görünümü veya pencere sınıfında denetimi bildirin.

1. Denetimin üye [Oluştur](reference/ctabctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CDateTimeCtrl Kullanma](using-cdatetimectrl.md)<br/>
[Denetimler](controls-mfc.md)
