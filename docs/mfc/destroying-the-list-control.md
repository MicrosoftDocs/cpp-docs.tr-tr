---
title: Listesi denetimini yok etme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fdaafb8a6951050dac0022e0e6e8874b48d688e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-list-control"></a>Listesi Denetimini Yok Etme
Katıştırılmış içerirse, [CListCtrl](../mfc/reference/clistctrl-class.md) nesne bir görünüm veya iletişim sınıfı veri üyesi olarak sahibi bozulduğunda yok. Kullanırsanız, bir [CListView](../mfc/reference/clistview-class.md), görünüm bozar zaman framework denetimi yok eder.  
  
 Liste denetimi yerine uygulama depolanması için liste verilerinizden bazıları için düzenleme, kendi ayırmayı kaldırma için düzenlemek gerekir. Daha fazla bilgi için bkz: [geri çağrı öğeleri ve geri çağrı maskesi](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK'sındaki.  
  
 Ayrıca, oluşturduğunuz ve liste denetimi nesnesiyle ilişkili resim listeleri ayırmasını kaldırma için sorumlu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

