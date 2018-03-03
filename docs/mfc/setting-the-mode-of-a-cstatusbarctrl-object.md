---
title: Bir CStatusBarCtrl nesnesinin modunu ayarlama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c954354321d814952ec3ac5ea148cc9177cd0fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl Nesnesinin Modunu Ayarlama
İçin iki modda bir `CStatusBarCtrl` nesnesi: Basit ve basit olmayan. Çoğu durumda, metin ve belki de bir simge veya simgeleri birlikte bir veya daha fazla bölümleri durum çubuğu denetimine sahip olur. Bu basit olmayan mod adı verilir. Bu modu hakkında daha fazla bilgi için bkz: [CStatusBarCtrl nesnesinin bölümlerini başlatma](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Ancak, burada yalnızca tek bir metin satırının görüntülemeniz durumlar vardır. Bu durumda, basit mod gereksinimleriniz için yeterli olur. Modunu değiştirmek için `CStatusBarCtrl` nesne için basit, çağırmaya [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) üye işlevi. Durum çubuğu denetimi basit modda olduğunda, metin aranarak **SetText** değeri olarak 255 geçirme üye işlevi **nPane** parametresi.  
  
 Kullanabileceğiniz [Issimple](../mfc/reference/cstatusbarctrl-class.md#issimple) modu belirlemek için işlevi `CStatusBarCtrl` nesne.  
  
> [!NOTE]
>  Durum çubuğu nesnesi nonsimple basit değiştirilirken veya tersi, pencerenin hemen yeniden ve uygulanabilirse tanımlanan tüm bölümleri otomatik olarak geri yüklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

