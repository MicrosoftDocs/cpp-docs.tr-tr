---
title: Bir CStatusBarCtrl nesnesinin modunu ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdad5073b3f566ad43d25258ca0b5e173f52fb57
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956817"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl Nesnesinin Modunu Ayarlama
İçin iki modda bir `CStatusBarCtrl` nesnesi: Basit ve basit olmayan. Çoğu durumda, metin ve belki de bir simge veya simgeleri birlikte bir veya daha fazla bölümleri durum çubuğu denetimine sahip olur. Bu basit olmayan mod adı verilir. Bu modu hakkında daha fazla bilgi için bkz: [CStatusBarCtrl nesnesinin bölümlerini başlatma](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Ancak, burada yalnızca tek bir metin satırının görüntülemeniz durumlar vardır. Bu durumda, basit mod gereksinimleriniz için yeterli olur. Modunu değiştirmek için `CStatusBarCtrl` nesne için basit, çağırmaya [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) üye işlevi. Durum çubuğu denetimi basit modda olduğunda, metin aranarak `SetText` değeri olarak 255 geçirme üye işlevi *nPane* parametresi.  
  
 Kullanabileceğiniz [Issimple](../mfc/reference/cstatusbarctrl-class.md#issimple) modu belirlemek için işlevi `CStatusBarCtrl` nesne.  
  
> [!NOTE]
>  Durum çubuğu nesnesi nonsimple basit değiştirilirken veya tersi, pencerenin hemen yeniden ve uygulanabilirse tanımlanan tüm bölümleri otomatik olarak geri yüklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

