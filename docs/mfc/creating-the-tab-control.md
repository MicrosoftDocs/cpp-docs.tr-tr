---
title: Sekme denetimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
dev_langs:
- C++
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3945d441130d723bbda3d137f2adae637d56c2b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344097"
---
# <a name="creating-the-tab-control"></a>Sekme Denetimi Oluşturma
Sekme denetimi nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.  
  
### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>CTabCtrl doğrudan iletişim kutusunda kullanmak için  
  
1.  İletişim kutusu Düzenleyicisi'nde bir sekme denetimi, iletişim şablon kaynağı ekleyin. Denetim kimliği belirtin.  
  
2.  Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CTabCtrl](../mfc/reference/ctabctrl-class.md) denetim özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CTabCtrl` üye işlevleri.  
  
3.  İşleyici işlevleri işlemek için gereken tüm sekme denetimi bildirim iletilerini iletişim sınıfında eşleyin. Daha fazla bilgi için bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).  
  
4.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), stilleri ayarlama `CTabCtrl`.  
  
### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>CTabCtrl nondialog penceresinde kullanmak için  
  
1.  Denetim görünüm veya penceresi sınıfında tanımlayın.  
  
2.  Denetimin çağrısı [oluşturma](../mfc/reference/ctabctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, üst pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.  
  
 Sonra `CTabCtrl` nesnesi oluşturulamadı, ayarlama veya stilleri genişletilmiş aşağıdaki temizleyin:  
  
-   **TCS_EX_FLATSEPARATORS** sekme denetimi sekme öğeleri arasında ayırıcılar çizer. Denetimleri etkiler sekmesi yalnızca bu genişletilmiş stili **TCS_BUTTONS** ve **TCS_FLATBUTTONS** stilleri. Varsayılan olarak, sekme denetimi oluşturma **TCS_FLATBUTTONS** stilini ayarlar bu genişletilmiş stili.  
  
-   **TCS_EX_REGISTERDROP** sekme denetimi oluşturur **TCN_GETOBJECT** bir bırakma hedefi istemek için bildirim iletilerini nesne bir nesne denetiminde sekme öğeleri üzerinden sürüklendiğinde.  
  
    > [!NOTE]
    >  Almak için **TCN_GETOBJECT** bildirim, OLE kitaplıklarının çağrısıyla başlatmak gerekir [Afxoleınit](../mfc/reference/ole-initialization.md#afxoleinit).  
  
 Bu stiller alınır ve ayarlama denetimi, ilgili yapılan çağrılarla oluşturulduktan sonra [GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) ve [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) üye işlevleri.  
  
 Örneğin, ayarlamak **TCS_EX_FLATSEPARATORS** aşağıdaki kod satırlarını stiliyle:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]  
  
 Clear **TCS_EX_FLATSEPARATORS** gelen stil bir `CTabCtrl` aşağıdaki kod satırlarını nesnesiyle:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]  
  
 Bu düğmelerinin arasında görünür ayırıcılar kaldırır, `CTabCtrl` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

