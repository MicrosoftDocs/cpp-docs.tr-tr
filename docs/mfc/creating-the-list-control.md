---
title: "Liste denetimi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85afbe49943e06a66cf2fa914cc87f07b0fa8c52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-list-control"></a>Liste Denetimi Oluşturma
Listenin nasıl kontrol ([CListCtrl](../mfc/reference/clistctrl-class.md)) oluşturulan denetimi kullanarak doğrudan mı sınıfını kullanarak üzerinde bağlıdır [CListView](../mfc/reference/clistview-class.md) yerine. Kullanırsanız `CListView`, çerçeve, belge/görünüm oluşturma dizisi bir parçası olarak görünümü oluşturur. Liste görünümü oluşturma (ikisi de aynı olan) liste denetimi de oluşturur. Denetim görünümün içinde oluşturulan [OnCreate](../mfc/reference/cwnd-class.md#oncreate) işleyici işlevi. Bu durumda, Denetim çağrısıyla öğeler eklemek hazır [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl).  
  
### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>CListCtrl doğrudan iletişim kutusunda kullanmak için  
  
1.  İletişim kutusu Düzenleyicisi'nde, liste denetimi, iletişim şablon kaynağı ekleyin. Denetim kimliği belirtin.  
  
2.  Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için `CListCtrl` denetim özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CListCtrl` üye işlevleri.  
  
3.  Tanıtıcı gereken herhangi bir liste denetimi bildirim iletileri için iletişim kutusu sınıfı işleyici işlevlerde eşlemek için Özellikler penceresini kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
4.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), stilleri ayarlama `CListCtrl`. Bkz: [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md). Görünümü daha sonra değiştirebilirsiniz, ancak bu tür bir "denetiminde alma Görünüm" belirler.  
  
### <a name="to-use-clistctrl-in-a-nondialog-window"></a>CListCtrl nondialog penceresinde kullanmak için  
  
1.  Denetim görünüm veya penceresi sınıfında tanımlayın.  
  
2.  Denetimin çağrısı [oluşturma](../mfc/reference/clistctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, üst pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

