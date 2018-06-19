---
title: Yazdırma ve Baskı Önizleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a26bac196dbddc6c05df5850225d05f432bc566
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346262"
---
# <a name="printing-and-print-preview"></a>Yazdırma ve Baskı Önizleme
MFC sınıf aracılığıyla programınızın belgeler için yazdırma ve baskı önizlemeyi destekleyen [CView](../mfc/reference/cview-class.md). Temel yazdırma ve Baskı Önizleme için Görünüm sınıfınızın yalnızca geçersiz kılma [OnDraw](../mfc/reference/cview-class.md#ondraw) yine de yapmalısınız üye işlevi. Ekranda, gerçek bir yazıcı için bir yazıcı aygıt içeriği görüntülemek için bu işlevi çizebilirsiniz veya bir cihaz bağlamına, yazıcınızın ekranında benzetimini yapar.  
  
 Birden çok belge yazdırma ve Önizleme, yazdırılan belgeleri sayfalara bölme ve üstbilgiler ve altbilgiler bunlara eklemek için yönetmek için kod de ekleyebilirsiniz.  
  
 Bu makaleler ailesi yazdırma Microsoft Foundation Class Kitaplığı (MFC) nasıl uygulandığını ve zaten Framework'e yerleştirilmiş yazdırma mimarisi yararlanmak nasıl açıklanmaktadır. Makaleleri nasıl MFC kolay yazdırma önizleme işlevini destekliyor ve nasıl kullanın ve bu işlevselliği değiştirmek de açıklanmaktadır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Yazdırma](../mfc/printing.md)  
  
-   [Baskı Önizleme mimarisi](../mfc/print-preview-architecture.md)  
  
-   [Örnek](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
