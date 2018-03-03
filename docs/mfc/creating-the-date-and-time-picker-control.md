---
title: "Tarih ve Saat Seçici denetimini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9c0b99f42bef162ed3c571e19630f9227a8504e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-date-and-time-picker-control"></a>Tarih ve Saat Seçici Denetimini Oluşturma
Tarih ve Saat Seçici denetimini nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.  
  
### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>CDateTimeCtrl doğrudan iletişim kutusunda kullanmak için  
  
1.  İletişim kutusu Düzenleyicisi'nde bir tarih ve Saat Seçici denetim, iletişim şablon kaynağı ekleyin. Denetim kimliği belirtin.  
  
2.  Tarih ve Saat Seçici denetim özellikleri iletişim kutusunu kullanarak gerekli stilleri belirtin.  
  
3.  Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) denetim özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CDateTimeCtrl` üye işlevleri.  
  
4.  İşleyici işlevleri herhangi bir tarih saat seçici denetimi için iletişim kutusu sınıfında eşlemek için Özellikler penceresini kullanın [bildirim](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) iletileri işlemek gerekir (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), tüm ek stillerini ayarlama `CDateTimeCtrl` nesnesi.  
  
### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>CDateTimeCtrl nondialog penceresinde kullanmak için  
  
1.  Görünüm veya penceresi sınıfında denetimi bildirin.  
  
2.  Denetimin çağrısı [oluşturma](../mfc/reference/ctabctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, üst pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

