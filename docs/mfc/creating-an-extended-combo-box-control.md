---
title: Genişletilmiş Birleşik giriş kutusu denetimi oluşturma | Microsoft Docs
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
ms.openlocfilehash: 7c6a891aeadf2fa8366eec52a967e13776db6523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341218"
---
# <a name="creating-an-extended-combo-box-control"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimi Oluşturma
Genişletilmiş Birleşik giriş kutusu denetimi nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.  
  
### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>CComboBoxEx doğrudan iletişim kutusunda kullanmak için  
  
1.  İletişim kutusu Düzenleyicisi'nde bir Genişletilmiş Birleşik giriş kutusu denetimi, iletişim şablon kaynağı ekleyin. Denetim kimliği belirtin.  
  
2.  Genişletilmiş Birleşik giriş kutusu denetiminin özellikleri iletişim kutusunu kullanarak, gerekli stilleri belirtin.  
  
3.  Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) denetim özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CComboBoxEx` üye işlevleri.  
  
4.  İşleyici işlevleri işlemek için gereken tüm Genişletilmiş Birleşik giriş kutusu denetimi bildirim iletileri için iletişim kutusu sınıfında eşlemek için Özellikler penceresini kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), tüm ek stillerini ayarlama `CComboBoxEx` nesnesi.  
  
### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>CComboBoxEx nondialog penceresinde kullanmak için  
  
1.  Denetim görünüm veya penceresi sınıfında tanımlayın.  
  
2.  Denetimin çağrısı [oluşturma](../mfc/reference/ctabctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, üst pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) işleyici işlevi. Denetimi için stiller ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComboBoxEx kullanma](../mfc/using-ccomboboxex.md)   
 [Denetimler](../mfc/controls-mfc.md)

