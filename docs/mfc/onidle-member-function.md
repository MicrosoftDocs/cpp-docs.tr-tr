---
title: "ONIDLE üye işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OnIdle
dev_langs: C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d601ac8da59e4b980c4f1a5bd85bc1b347e8e11e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi
Windows iletileri işlenmekteyken framework çağırması [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) (MFC Kitaplığı Başvurusu'nda açıklanan).  
  
 Geçersiz kılma `OnIdle` arka plan görevleri gerçekleştirmek için. Varsayılan sürüm araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri durumunu güncelleştirir ve temizleme işlemlerini esnasında framework tarafından oluşturulan geçici nesneler işlemini gerçekleştirir. Aşağıdaki şekilde nasıl ileti döngüsü çağırır gösterilmektedir `OnIdle` sıraya ileti olduğunda.  
  
 ![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "vc387c1")  
İleti döngüsü  
  
 Boşta döngü içinde neler yapabileceğiniz hakkında daha fazla bilgi için bkz: [boşta döngü işleme](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
