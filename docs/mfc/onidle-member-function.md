---
title: "ONIDLE üye işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfbc0a1f20cb6cc01143ed6f07a63e84b53be6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi
Windows iletileri işlenmekteyken framework çağırması [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) (MFC Kitaplığı Başvurusu'nda açıklanan).  
  
 Geçersiz kılma `OnIdle` arka plan görevleri gerçekleştirmek için. Varsayılan sürüm araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri durumunu güncelleştirir ve temizleme işlemlerini esnasında framework tarafından oluşturulan geçici nesneler işlemini gerçekleştirir. Aşağıdaki şekilde nasıl ileti döngüsü çağırır gösterilmektedir `OnIdle` sıraya ileti olduğunda.  
  
 ![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "vc387c1")  
İleti döngüsü  
  
 Boşta döngü içinde neler yapabileceğiniz hakkında daha fazla bilgi için bkz: [boşta döngü işleme](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
