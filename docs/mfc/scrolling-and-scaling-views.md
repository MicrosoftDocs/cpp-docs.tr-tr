---
title: Görünümleri kaydırma ve ölçeklendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8bd42a7da91f984c4cedc4deafc0ab9f4417495
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scrolling-and-scaling-views"></a>Görünümleri Kaydırma ve Ölçeklendirme
MFC kaydırın ve görünümler otomatik olarak bunları görüntüler çerçeve penceresi boyutunu ölçeklenir görünümleri destekler. Sınıf `CScrollView` görünümler her iki tür destekler.  
  
 Kaydırma ve ölçeklendirme hakkında daha fazla bilgi için bkz [CScrollView](../mfc/reference/cscrollview-class.md) içinde *MFC başvurusu*. Kayan bir örnek için bkz: [karalama örnek](../visual-cpp-samples.md).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   Bir görünümü kaydırma  
  
-   Bir görünüm ölçeklendirme  
  
-   [Görünümü koordinatları](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a>Bir görünümü kaydırma  
 Sık bir belgeyi kendi görünümü görüntüleyebilir boyutundan büyük boyutudur. Bu belgenin veri artırır veya kullanıcı görünüm çerçeve penceresi küçültür nedeniyle oluşabilir. Böyle durumlarda, kaydırma görünümü desteklemesi gerekir.  
  
 Herhangi bir görünüm kaydırma çubuğu iletileri işleyebilir kendi `OnHScroll` ve `OnVScroll` üye işlevleri. Tüm iş kendiniz yapmadan ya da uygulama kaydırma çubuğu ileti işleme bu işlevlerinde olabilir ya da kullanabilirsiniz `CScrollView` sizin için kaydırma işlemek için sınıf.  
  
 `CScrollView`şunları yapar:  
  
-   Pencere ve görünüm penceresinin boyutlarını ve eşleme modları yönetir  
  
-   Kaydırma çubuğu iletilere yanıt olarak otomatik olarak kayar  
  
 Ne kadar (kullanıcının bir kaydırma ok tıkladığında) "(kullanıcı bir kaydırma çubuğunun mil tıklattığında) bir sayfa" ve "satır" kaydırmak için belirtebilirsiniz. Görünümünüzü yapısını uyacak şekilde bu değerleri planlayın. Örneğin, bir grafik görünümü için 1 piksel artışlarla ancak metin belgelerde satır yüksekliği göre artışlarla kaydırma isteyebilirsiniz.  
  
##  <a name="_core_scaling_a_view"></a>Bir görünüm ölçeklendirme  
 Görünümü otomatik olarak kendi çerçeve penceresi sığacak şekilde istediğinizde kullanabilirsiniz `CScrollView` kaydırma yerine ölçekleme için. Mantıksal görünüm uzatılabilir ya da pencerenin istemci alanını tam olarak sığması için küçültülebilir. Kaydırma çubukları ölçeklendirilmiş bir görünüm içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görünümleri Kullanma](../mfc/using-views.md)

