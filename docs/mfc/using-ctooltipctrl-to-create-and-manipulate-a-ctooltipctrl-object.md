---
title: CToolTipCtrl kullanarak bir CToolTipCtrl nesnesi oluşturma ve | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2143ea37cfe9448e43aacfa75622beab93d2fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme
Bir örneği burada verilmiştir [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) kullanımı:  
  
### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Oluşturma ve bir CToolTipCtrl  
  
1.  Oluşturmak `CToolTipCtrl` nesnesi.  
  
2.  Çağrı [oluşturma](../mfc/reference/ctooltipctrl-class.md#create) Windows araç ipucunu ortak denetimini oluşturmak ve ona eklemek için `CToolTipCtrl` nesnesi.  
  
3.  Çağrı [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) imleci araç olduğunda araç ipucunda depolanan bilgileri görüntülenir böylece araç ipucunu denetimini ile bir aracı kaydetmek için.  
  
4.  Çağrı [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) bir araç için bir araç ipucu tutar bilgisi özelliğini ayarlamalısınız.  
  
5.  Çağrı [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) bir aracı için yeni bir sınırlayıcı dikdörtgenini ayarlamak için.  
  
6.  Çağrı [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) verilen aracı sınırlayıcı dikdörtgenini içinde olup olmadığını ve bu durumda belirlemek için bir noktası sınamak için araç hakkında bilgi alın.  
  
7.  Çağrı [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) araç ipucunu denetimini ile kayıtlı araçları sayısı alınamadı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

