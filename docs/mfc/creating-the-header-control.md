---
title: "Üstbilgi denetimi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c47e458d4cd6e9df556eef5e1f61806633208011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-header-control"></a>Üstbilgi Denetimi Oluşturma
Üstbilgi denetimi (üstbilgi denetimi içeren bir liste denetimini ekleyebilseniz) doğrudan iletişim kutusu Düzenleyicisi'nde kullanılabilir değil.  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>Üstbilgi denetimi iletişim kutusuna yerleştirin  
  
1.  El ile türündeki üye değişkeni ekleme [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) iletişim sınıfınızda.  
  
2.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), oluşturma ve stillerini ayarlama `CHeaderCtrl`konumlandırın ve görüntüleyin.  
  
3.  Üstbilgi denetimine öğe ekleyin.  
  
4.  Tanıtıcı gereken herhangi bir üstbilgi denetimi bildirim iletileri için iletişim kutusu sınıfı işleyici işlevlerde eşlemek için Özellikler penceresini kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Üstbilgi denetimi görünümünde (CListView değil) yerleştirilecek  
  
1.  Embed bir [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) görünüm sınıfınızda nesnesi.  
  
2.  Stili, konumu ve üstbilgi denetimi penceresi 's görüntülemek [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) üye işlevi.  
  
3.  Üstbilgi denetimine öğe ekleyin.  
  
4.  Tanıtıcı gereken herhangi bir üstbilgi denetimi bildirim iletileri için view sınıfı işleyici işlevlerde eşlemek için Özellikler penceresini kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).  
  
 Görünüm ya da iletişim nesnesi oluşturulduğunda, her iki durumda da, katıştırılmış denetim nesnesi oluşturulur. Çağırmalısınız sonra [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) denetimi penceresi oluşturulamadı. Denetim konumlandırmak için çağrı [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) denetimin ilk boyutunu ve konumunu belirlemek için ve [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) istediğiniz yere ayarlamak için. Daha sonra açıklandığı gibi öğeleri Ekle [üstbilgi denetimine öğe eklemeyi](../mfc/adding-items-to-the-header-control.md).  
  
 Daha fazla bilgi için bkz: [üstbilgi denetimi oluşturma](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeaderCtrl kullanma](../mfc/using-cheaderctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

