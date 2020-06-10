---
title: Liste Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: c9ba379611c44b5eae8d02b908ba71e3dbd66481
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617104"
---
# <a name="creating-the-list-control"></a>Liste Denetimi Oluşturma

Liste denetiminin ([CListCtrl](reference/clistctrl-class.md)) nasıl oluşturulduğu, denetimi doğrudan mi yoksa bunun yerine bir sınıf [clienstview](reference/clistview-class.md) kullanarak mı kullandığınıza bağlıdır. Kullanıyorsanız Framework, `CListView` görünümü belge/görünüm oluşturma sırasının bir parçası olarak oluşturur. Liste görünümü oluşturulduğunda liste denetimi de oluşturulur (ikisi de aynı şeydir). Denetim, görünümün [OnCreate](reference/cwnd-class.md#oncreate) işleyici işlevinde oluşturulur. Bu durumda, denetim bir [GetListCtrl](reference/clistview-class.md#getlistctrl)çağrısıyla öğe eklemeye hazırız.

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>Doğrudan bir iletişim kutusunda CListCtrl ' i kullanmak için

1. İletişim kutusu düzenleyicisinde iletişim kutusu şablonu kaynağına bir liste denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Denetim özelliği ile türünde bir üye değişkeni eklemek için [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md) ' nı kullanın `CListCtrl` . Bu üyeyi, üye işlevlerini çağırmak için kullanabilirsiniz `CListCtrl` .

1. İşlemek için gerekli olan herhangi bir liste denetimi bildirim iletisi için iletişim kutusu sınıfındaki işleyici işlevlerini eşlemek için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)' da, için stilleri ayarlayın `CListCtrl` . Bkz. [liste denetim stillerini değiştirme](changing-list-control-styles.md). Bu, görünümü daha sonra değiştirebilseniz de, denetimde aldığınız "Görünüm" türünü belirler.

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CListCtrl ' i kullanmak için

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](reference/clistctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
