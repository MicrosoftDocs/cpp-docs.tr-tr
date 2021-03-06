---
description: 'Hakkında daha fazla bilgi edinin: aylık Takvim denetimi oluşturma'
title: Aylık Takvim Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
ms.openlocfilehash: 98c707e16f05a8f5e4d3b42e3c9504f74e4aca29
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309530"
---
# <a name="creating-the-month-calendar-control"></a>Aylık Takvim Denetimi Oluşturma

Aylık Takvim denetimi, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>CMonthCalCtrl ' i doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde, iletişim şablonu kaynağına bir aylık Takvim denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Aylık takvim denetiminin Özellikler iletişim kutusunu kullanarak gereken stilleri belirtin.

1. Denetim özelliğiyle [CMonthCalCtrl](reference/cmonthcalctrl-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı 'nı](../ide/adding-a-member-variable-visual-cpp.md) kullanın. Bu üyeyi, üye işlevlerini çağırmak için kullanabilirsiniz `CMonthCalCtrl` .

1. İşlemek istediğiniz herhangi bir ay Takvim denetimi bildirim iletisi için İletişim sınıfındaki işleyici işlevlerini eşlemek için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)' da nesne için ek stiller ayarlayın `CMonthCalCtrl` .

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CMonthCalCtrl kullanma

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](reference/cmonthcalctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](using-cmonthcalctrl.md)<br/>
[Denetimler](controls-mfc.md)
