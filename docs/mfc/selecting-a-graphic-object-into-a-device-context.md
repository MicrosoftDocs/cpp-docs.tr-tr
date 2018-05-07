---
title: Bir cihaz bağlamına grafik nesnesi seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc605be317d51c985e32fbad038d846b056e5fe6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
  
-   [Bir Görünümde Çizim Yapma](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik Nesneler](../mfc/graphic-objects.md)

