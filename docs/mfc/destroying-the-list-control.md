---
title: Listesi denetimini yok etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edb26671ba775cfa7daf98d39c7eccc9fd4111bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343288"
---
# <a name="destroying-the-list-control"></a>Listesi Denetimini Yok Etme
Katıştırılmış içerirse, [CListCtrl](../mfc/reference/clistctrl-class.md) nesne bir görünüm veya iletişim sınıfı veri üyesi olarak sahibi bozulduğunda yok. Kullanırsanız, bir [CListView](../mfc/reference/clistview-class.md), görünüm bozar zaman framework denetimi yok eder.  
  
 Liste denetimi yerine uygulama depolanması için liste verilerinizden bazıları için düzenleme, kendi ayırmayı kaldırma için düzenlemek gerekir. Daha fazla bilgi için bkz: [geri çağrı öğeleri ve geri çağrı maskesi](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows SDK'sındaki.  
  
 Ayrıca, oluşturduğunuz ve liste denetimi nesnesiyle ilişkili resim listeleri ayırmasını kaldırma için sorumlu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

