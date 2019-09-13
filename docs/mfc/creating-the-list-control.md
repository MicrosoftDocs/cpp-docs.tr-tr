---
title: Liste Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: f1c5d8db93421e1d3ae0e39aec82bdf0f5529f1f
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907919"
---
# <a name="creating-the-list-control"></a>Liste Denetimi Oluşturma

Liste denetiminin ([CListCtrl](../mfc/reference/clistctrl-class.md)) nasıl oluşturulduğu, denetimi doğrudan mi yoksa bunun yerine bir sınıf [clienstview](../mfc/reference/clistview-class.md) kullanarak mı kullandığınıza bağlıdır. `CListView`Kullanıyorsanız Framework, görünümü belge/görünüm oluşturma sırasının bir parçası olarak oluşturur. Liste görünümü oluşturulduğunda liste denetimi de oluşturulur (ikisi de aynı şeydir). Denetim, görünümün [OnCreate](../mfc/reference/cwnd-class.md#oncreate) işleyici işlevinde oluşturulur. Bu durumda, denetim bir [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)çağrısıyla öğe eklemeye hazırız.

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Doğrudan bir iletişim kutusunda CListCtrl ' i kullanmak için

1. İletişim kutusu düzenleyicisinde iletişim kutusu şablonu kaynağına bir liste denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Denetim özelliği ile türünde `CListCtrl` bir üye değişkeni eklemek için [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md) ' nı kullanın. Bu üyeyi, üye işlevlerini çağırmak `CListCtrl` için kullanabilirsiniz.

1. İşlemek için gerekli olan herhangi bir liste denetimi bildirim iletisi için iletişim kutusu sınıfındaki işleyici işlevlerini eşlemek için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)' da, `CListCtrl`için stilleri ayarlayın. Bkz. [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md). Bu, görünümü daha sonra değiştirebilseniz de, denetimde aldığınız "Görünüm" türünü belirler.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CListCtrl ' i kullanmak için

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](../mfc/reference/clistctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
