---
title: Yazdırma ve Baskı Önizleme
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
ms.openlocfilehash: 70740922ec7f2030d14eebee72144a373550aacc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768893"
---
# <a name="printing-and-print-preview"></a>Yazdırma ve Baskı Önizleme

MFC sınıfı aracılığıyla programınızın belgeler için yazdırma ve yazdırma önizleme destekler [CView](../mfc/reference/cview-class.md). Temel yazdırma ve baskı önizlemeyi için Görünüm sınıfın yalnızca geçersiz kılma [OnDraw](../mfc/reference/cview-class.md#ondraw) yine de yapmalısınız üye işlevi. Bu işlev için Görünüm ekranında, gerçek bir yazıcı için bir yazıcı cihaz bağlamına çizebilirsiniz veya bir cihaz bağlamına, ekranda yazıcınızın benzetimini yapar.

Ayrıca, birden çok belge yazdırma ve Önizleme, yazdırılan belgeleri gösterilecek şekilde sayfalara bölmek ve üstbilgiler ve altbilgiler eklemek üzere yönetmek için kod ekleyebilirsiniz.

Bu makaleler ailesi yazdırma Microsoft Foundation Class Kitaplığı (MFC) nasıl uygulandığını ve nasıl yararlanabileceğinizi altyapısına zaten oluşturulmuş yazdırma mimarisi açıklanmaktadır. Makaleler de MFC kolay uygulama baskı önizlemeyi işlevselliğinin nasıl desteklediğini ve nasıl kullanın ve bu işlevselliğini değiştirmenize açıklamaktadır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Yazdırma](../mfc/printing.md)

- [Baskı Önizleme mimarisi](../mfc/print-preview-architecture.md)

- [Örnek](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
