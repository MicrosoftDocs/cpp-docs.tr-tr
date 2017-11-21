---
title: "Nesnelerin tek aşamalı ve iki aşamalı yapımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f3e337f96c1acef53b1ec34237d31a868fb4dfe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı
İki kalemler ve fırçalar gibi grafik nesneleri oluşturma tekniği arasında seçim yapabilirsiniz:  
  
-   *Tek aşamalı yapımı*: yapısı ve tek bir aşamada Oluşturucusu ile tüm nesne başlatılamadı.  
  
-   *İki aşamalı yapımı*: yapısı ve iki ayrı aşamaları içinde nesne başlatılamadı. Nesne oluşturucusu oluşturur ve onu bir başlatma işlevi başlatır.  
  
 İki aşamalı yapımı her zaman daha güvenlidir. Tek aşamalı yapısında Oluşturucusu bir özel durum yanlış bağımsız değişkenleri sağlayın veya bellek ayırma başarısız olursa durum oluşturabilir. İçin hatası denetlemek sahip olsa da bu sorunun iki aşamalı yapımı tarafından önlenmiş olur. Her iki durumda da, nesne yok etme aynı işlemidir.  
  
> [!NOTE]
>  Bu teknikler oluşturmak için herhangi bir nesneleri, yalnızca grafik nesneleri uygulanabilir.  
  
## <a name="example-of-both-construction-techniques"></a>Hem yapı teknikleri örneği  
 Aşağıdaki kısa örnek bir kalem nesnesi oluşturma, her iki yöntem gösterir:  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Grafik nesneleri](../mfc/graphic-objects.md)  
  
-   [Bir cihaz bağlamına grafik nesnesi seçme](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md)  
  
-   [Bir görünümde çizim yapma](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik nesneleri](../mfc/graphic-objects.md)

