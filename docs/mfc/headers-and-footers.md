---
title: "Üstbilgiler ve altbilgiler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7525cba7d05c4d04f0548bd2dc774503b284c220
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="headers-and-footers"></a>Üstbilgiler ve Altbilgiler
Bu makalede, yazdırılan belgeye üstbilgiler ve altbilgiler ekleme açıklanmaktadır.  
  
 Ekranda zamanında bir belgeye baktığınızda, belge ve geçerli konumunuz belgedeki adını yaygın olarak görüntülenir bir başlık çubuğu ve durum çubuğu. Bir belgenin basılı kopya ararken bir üstbilgisinde veya altbilgisinde gösterilen adı ve sayfa numarası yararlıdır. Bu, hangi bile WYSIWYG içinde nasıl yazdırma ve ekran görüntüsü gerçekleştirdikleri içinde programlar farklı genel bir yoludur.  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi yerdir her bir sayfa için çağrıldığı için ve ekran görüntüsü için yazdırma için yalnızca çağrıldığı için üstbilgiler ve altbilgiler yazdırmak için uygun. Üstbilgisinde veya altbilgisinde yazdırmak için ayrı bir işleve tanımlayın ve yazıcı aygıt bağlamdan geçirin `OnPrint`. Pencere kaynak ya da uzantısı çağırmadan önce ayarlamanız gerekebilir [OnDraw](../mfc/reference/cview-class.md#ondraw) üstbilgisinde veya altbilgisinde sayfa örtüşme gövdesi zorunda kalmamak için. Aynı zamanda değiştirmeniz gerekebilir `OnDraw` uygun belge miktarını sayfasında azaltılabilir olduğundan.  
  
 Üstbilginin veya altbilginin tarafından harcanan alan kullanmak için dengelemek için tek yönlü **m_rectDraw** üyesi [Cprintınfo](../mfc/reference/cprintinfo-structure.md). Her zaman bir sayfa yazdırılır, bu üye sayfanın kullanılabilir alanı ile başlatıldı. Sayfa gövdesi yazdırma önce üstbilgisinde veya altbilgisinde yazdırma, depolanan dikdörtgen boyutunu küçültebilirsiniz **m_rectDraw** üstbilgisinde veya altbilgisinde tarafından harcanan alan hesaba. Ardından `OnPrint` başvurabilirsiniz **m_rectDraw** sayfasının gövdesi yazdırmak için ne kadar alan kalır çıkışı bulunamıyor.  
  
 Üst bilgi veya alanından başka bir şey yazdırılamıyor [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc), önce çağrıldığı için `StartPage` üye işlevini [CDC](../mfc/reference/cdc-class.md) çağrıldı. Bu noktada, yazıcı cihaz bağlamı bir sayfa sınırında olarak kabul edilir. Yazdırma yalnızca gerçekleştirebilirsiniz `OnPrint` üye işlevi.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Birden çok belge yazdırma](../mfc/multipage-documents.md)  
  
-   [Yazdırma için GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)

