---
title: Tarih ve Saat Seçici denetimini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 864d6cfef599da61238baa92f7ab01a8ad82229d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393301"
---
# <a name="creating-the-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetimini Oluşturma

Tarih ve Saat Seçici denetiminin nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>CDateTimeCtrl doğrudan iletişim kutusunda kullanmak için

1. İletişim kutusu Düzenleyicisi'nde iletişim şablonu kaynağınıza bir tarih ve Saat Seçici denetimini ekleyin. Denetim kimliğini belirtin

1. Tarih ve Saat Seçici denetiminin özellikleri iletişim kutusunu kullanarak gerekli tüm stilleri belirtin.

1. Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) denetimi özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CDateTimeCtrl` üye işlevleri.

1. Herhangi bir tarih saat seçici denetimi için iletişim kutusu sınıfı işleyici işlevleri eşlemek için Özellikler penceresini kullanın [bildirim](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) iletileri işlemek için (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), ayarlamak için ek stilleri `CDateTimeCtrl` nesne.

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>CDateTimeCtrl nondialog penceresinde kullanmak için

1. Görünüm veya penceresi sınıfında denetimi bildirin.

1. Denetimin çağrı [Oluştur](../mfc/reference/ctabctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, ana pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.

## <a name="see-also"></a>Ayrıca Bkz.

[CDateTimeCtrl Kullanma](../mfc/using-cdatetimectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

