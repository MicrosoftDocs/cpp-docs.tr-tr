---
title: Aylık Takvim Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
ms.openlocfilehash: 809bc9fdf6b4477363d0a43d007a2884bb43a049
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242193"
---
# <a name="creating-the-month-calendar-control"></a>Aylık Takvim Denetimi Oluşturma

Aylık takvim denetiminin nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>CMonthCalCtrl doğrudan iletişim kutusunda kullanmak için

1. İletişim kutusu Düzenleyicisi'nde, bir ay takvimi iletişim şablonu kaynağınıza ekleyin. Denetim kimliğini belirtin

1. Aylık takvim denetiminin özellikleri iletişim kutusunu kullanarak, gerekli tüm stilleri belirtin.

1. Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) denetimi özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CMonthCalCtrl` üye işlevleri.

1. Özellikler penceresinde, herhangi bir ay Takvim denetimi bildirim iletileri için iletişim kutusu sınıfı işleyici işlevleri eşleştirmek için gereken işlemek için kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), ayarlamak için ek stilleri `CMonthCalCtrl` nesne.

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>CMonthCalCtrl nondialog penceresinde kullanmak için

1. Denetim görünüm veya pencere sınıfı tanımlayın.

1. Denetimin çağrı [Oluştur](../mfc/reference/cmonthcalctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, ana pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
