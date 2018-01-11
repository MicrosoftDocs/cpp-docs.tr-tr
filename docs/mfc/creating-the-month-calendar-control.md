---
title: "Aylık takvim denetimi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f55960177fa8bc9a31ebfd16b4dbc6aeaba3ee38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-month-calendar-control"></a>Aylık Takvim Denetimi Oluşturma
Aylık takvim denetiminin nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.  
  
### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>CMonthCalCtrl doğrudan iletişim kutusunda kullanmak için  
  
1.  İletişim kutusu Düzenleyicisi'nde bir aylık takvim denetiminin, iletişim şablon kaynağı ekleyin. Denetim kimliği belirtin.  
  
2.  Aylık takvim denetiminin, Özellikler iletişim kutusunu kullanarak, gerekli stilleri belirtin.  
  
3.  Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) denetim özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CMonthCalCtrl` üye işlevleri.  
  
4.  Tanıtıcı gereken herhangi bir ay Takvim denetimi bildirim iletileri için iletişim kutusu sınıfı işleyici işlevlerde eşlemek için Özellikler penceresini kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), tüm ek stillerini ayarlama `CMonthCalCtrl` nesnesi.  
  
### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>CMonthCalCtrl nondialog penceresinde kullanmak için  
  
1.  Denetim görünüm veya penceresi sınıfında tanımlayın.  
  
2.  Denetimin çağrısı [oluşturma](../mfc/reference/cmonthcalctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, üst pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMonthCalCtrl kullanma](../mfc/using-cmonthcalctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

