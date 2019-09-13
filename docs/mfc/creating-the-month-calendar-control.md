---
title: Aylık Takvim Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
ms.openlocfilehash: 9e430a86c2ac08bde0f031a4c91b9ae5c6f570f3
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907499"
---
# <a name="creating-the-month-calendar-control"></a>Aylık Takvim Denetimi Oluşturma

Aylık Takvim denetimi, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>CMonthCalCtrl ' i doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde, iletişim şablonu kaynağına bir aylık Takvim denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Aylık takvim denetiminin Özellikler iletişim kutusunu kullanarak gereken stilleri belirtin.

1. Denetim özelliğiyle [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı 'nı](../ide/adding-a-member-variable-visual-cpp.md) kullanın. Bu üyeyi, üye işlevlerini çağırmak `CMonthCalCtrl` için kullanabilirsiniz.

1. İşlemek istediğiniz herhangi bir ay Takvim denetimi bildirim iletisi için İletişim sınıfındaki işleyici işlevlerini eşlemek için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)' da `CMonthCalCtrl` nesne için ek stiller ayarlayın.

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CMonthCalCtrl kullanma

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](../mfc/reference/cmonthcalctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
