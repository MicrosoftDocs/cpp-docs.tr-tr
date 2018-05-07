---
title: ONIDLE üye işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbe912db448e424f18b6d72f6e148312c5940687
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="onidle-member-function"></a>OnIdle Üye İşlevi
Windows iletileri işlenmekteyken framework çağırması [CWinApp](../mfc/reference/cwinapp-class.md) üye işlevi [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) (MFC Kitaplığı Başvurusu'nda açıklanan).  
  
 Geçersiz kılma `OnIdle` arka plan görevleri gerçekleştirmek için. Varsayılan sürüm araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri durumunu güncelleştirir ve temizleme işlemlerini esnasında framework tarafından oluşturulan geçici nesneler işlemini gerçekleştirir. Aşağıdaki şekilde nasıl ileti döngüsü çağırır gösterilmektedir `OnIdle` sıraya ileti olduğunda.  
  
 ![İleti döngüsü işlemi](../mfc/media/vc387c1.gif "vc387c1")  
İleti döngüsü  
  
 Boşta döngü içinde neler yapabileceğiniz hakkında daha fazla bilgi için bkz: [boşta döngü işleme](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
