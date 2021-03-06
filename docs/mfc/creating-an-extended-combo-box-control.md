---
description: 'Daha fazla bilgi edinin: Genişletilmiş Birleşik giriş kutusu denetimi oluşturma'
title: Genişletilmiş Birleşik Giriş Kutusu Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: 93b4a24cfe4bf191e092d2456c5b6a62f79acc78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309985"
---
# <a name="creating-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimi Oluşturma

Genişletilmiş Birleşik giriş kutusu denetimi nasıl oluşturulur, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>CComboBoxEx 'ı doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde, iletişim kutusu şablonu kaynağına bir Genişletilmiş Birleşik giriş kutusu denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Genişletilmiş Birleşik giriş kutusu denetiminin Özellikler iletişim kutusunu kullanarak gereken stilleri belirtin.

1. Denetim özelliğiyle [CComboBoxEx](reference/ccomboboxex-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md) ' nı kullanın. Bu üyeyi, üye işlevlerini çağırmak için kullanabilirsiniz `CComboBoxEx` .

1. İşlemek için gereken Genişletilmiş Birleşik giriş kutusu denetim bildirim iletilerinin iletişim sınıfındaki işleyici işlevlerini eşlemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)' da nesne için ek stiller ayarlayın `CComboBoxEx` .

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CComboBoxEx kullanmak için

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](reference/ctabctrl-class.md#create) işlevini, muhtemelen üst pencerenin [OnCreate](reference/cwnd-class.md#oncreate) işleyici işlevi kadar erken bir şekilde [OnInitialUpdate](reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](using-ccomboboxex.md)<br/>
[Denetimler](controls-mfc.md)
