---
title: Genişletilmiş Birleşik Giriş Kutusu Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: 87e2e1cd3c29ba838a17c24ece4a89adda21db0c
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907733"
---
# <a name="creating-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimi Oluşturma

Genişletilmiş Birleşik giriş kutusu denetimi nasıl oluşturulur, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>CComboBoxEx 'ı doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde, iletişim kutusu şablonu kaynağına bir Genişletilmiş Birleşik giriş kutusu denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Genişletilmiş Birleşik giriş kutusu denetiminin Özellikler iletişim kutusunu kullanarak gereken stilleri belirtin.

1. Denetim özelliğiyle [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md) ' nı kullanın. Bu üyeyi, üye işlevlerini çağırmak `CComboBoxEx` için kullanabilirsiniz.

1. İşlemek için gereken Genişletilmiş Birleşik giriş kutusu denetim bildirim iletilerinin iletişim sınıfındaki işleyici işlevlerini eşlemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın (bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)' da `CComboBoxEx` nesne için ek stiller ayarlayın.

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CComboBoxEx kullanmak için

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](../mfc/reference/ctabctrl-class.md#create) işlevini, muhtemelen üst pencerenin [OnCreate](../mfc/reference/cwnd-class.md#oncreate) işleyici işlevi kadar erken bir şekilde [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
