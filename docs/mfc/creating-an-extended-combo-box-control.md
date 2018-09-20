---
title: Bir Genişletilmiş Birleşik giriş kutusu denetimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1a4a27e7d233f1ee6f68dbcfa2a70d3d50e9984
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394679"
---
# <a name="creating-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimi Oluşturma

Genişletilmiş Birleşik giriş kutusu denetimi nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>CComboBoxEx doğrudan iletişim kutusunda kullanmak için

1. İletişim kutusu Düzenleyicisi'nde iletişim şablonu kaynağınıza bir Genişletilmiş Birleşik giriş kutusu denetimini ekleyin. Denetim kimliğini belirtin

1. Genişletilmiş Birleşik giriş kutusu denetiminin özellikleri iletişim kutusunu kullanarak, gerekli tüm stilleri belirtin.

1. Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) denetimi özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CComboBoxEx` üye işlevleri.

1. İşleyici işlevlerini işlemek için gereken tüm Genişletilmiş Birleşik giriş kutusu denetimi bildirim iletileri için iletişim kutusu sınıfında eşlemek için Özellikler penceresini kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), ayarlamak için ek stilleri `CComboBoxEx` nesne.

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>CComboBoxEx nondialog penceresinde kullanmak için

1. Denetim görünüm veya pencere sınıfı tanımlayın.

1. Denetimin çağrı [Oluştur](../mfc/reference/ctabctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, ana pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) işleyicisi işlevi. Denetimi için stiller ayarlayın.

## <a name="see-also"></a>Ayrıca Bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

