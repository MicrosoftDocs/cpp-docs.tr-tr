---
title: Liste Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 7b2cb47699339dd413dc1bfae7623069da56e7a4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303659"
---
# <a name="creating-the-list-control"></a>Liste Denetimi Oluşturma

Listenin nasıl kontrol ([CListCtrl](../mfc/reference/clistctrl-class.md)) oluşturulur, denetimi kullanarak, doğrudan veya sınıfını kullanarak üzerinde bağlıdır [CListView](../mfc/reference/clistview-class.md) yerine. Kullanırsanız `CListView`, framework görünüm, belge/görünüm oluşturma dizisinin bir parçası oluşturur. Liste görünümü oluşturma (ikisi de aynı olan) listesi denetimi de oluşturur. Görünüme ait denetim oluşturulur [OnCreate](../mfc/reference/cwnd-class.md#oncreate) işleyicisi işlevi. Bu durumda, denetim için bir çağrı yoluyla bir öğe eklemek hazır [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>CListCtrl doğrudan iletişim kutusunda kullanmak için

1. İletişim kutusu Düzenleyicisi'nde iletişim şablonu kaynağınıza liste denetimi ekleyin. Denetim kimliğini belirtin

1. Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için `CListCtrl` denetimi özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CListCtrl` üye işlevleri.

1. Özellikler penceresinde, herhangi bir liste denetimi bildirim iletileri için iletişim kutusu sınıfı işleyici işlevleri eşleştirmek için gereken işlemek için kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), stillerini ayarlama `CListCtrl`. Bkz: [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md). Görünüm daha sonra değiştirebilirsiniz ancak bu "Görünüm denetiminde Al" türünü belirler.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>CListCtrl nondialog penceresinde kullanmak için

1. Denetim görünüm veya pencere sınıfı tanımlayın.

1. Denetimin çağrı [Oluştur](../mfc/reference/clistctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, ana pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
