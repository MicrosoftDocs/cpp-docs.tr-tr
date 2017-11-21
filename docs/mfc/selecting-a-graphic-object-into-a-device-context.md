---
title: "Bir cihaz bağlamına grafik nesnesi seçme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6ab8c783ac66af912d56ed44481c8c3968a70ca0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Bir Cihaz Bağlamına Grafik Nesnesi Seçme
Bu konu, grafik nesneleri pencerenin cihaz bağlamı kullanma için geçerlidir. Çalıştırdıktan sonra [bir çizim nesnesi oluşturmak](../mfc/one-stage-and-two-stage-construction-of-objects.md), depolanan varsayılan nesne yerine cihaz bağlamı içine seçmelisiniz:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## <a name="lifetime-of-graphic-objects"></a>Grafik nesnelerin ömrü  
 Grafik nesnesi tarafından döndürülen [SelectObject](../mfc/reference/cdc-class.md#selectobject) "geçici." Diğer bir deyişle, tarafından silinecek [ONIDLE](../mfc/reference/cwinapp-class.md#onidle) sınıfının üye işlevini `CWinApp` zamanı sonraki süresi program boşta alır. Tarafından döndürülen nesne kullandığınız sürece `SelectObject` denetimi için ana ileti döngüsü döndürmeden olmadan tek işlevi içinde herhangi bir sorun gerekir.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Grafik nesneleri](../mfc/graphic-objects.md)  
  
-   [Grafik nesnelerin tek aşamalı ve iki aşamalı yapımı](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md)  
  
-   [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik nesneleri](../mfc/graphic-objects.md)

