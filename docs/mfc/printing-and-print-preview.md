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
ms.openlocfilehash: 9aad5c69f6466ea8803cb466c5e5529f3dce1340
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374459"
---
# <a name="printing-and-print-preview"></a>Yazdırma ve Baskı Önizleme

MFC sınıfı aracılığıyla programınızın belgeler için yazdırma ve yazdırma önizleme destekler [CView](../mfc/reference/cview-class.md). Temel yazdırma ve baskı önizlemeyi için Görünüm sınıfın yalnızca geçersiz kılma [OnDraw](../mfc/reference/cview-class.md#ondraw) yine de yapmalısınız üye işlevi. Bu işlev için Görünüm ekranında, gerçek bir yazıcı için bir yazıcı cihaz bağlamına çizebilirsiniz veya bir cihaz bağlamına, ekranda yazıcınızın benzetimini yapar.

Ayrıca, birden çok belge yazdırma ve Önizleme, yazdırılan belgeleri gösterilecek şekilde sayfalara bölmek ve üstbilgiler ve altbilgiler eklemek üzere yönetmek için kod ekleyebilirsiniz.

Bu makaleler ailesi yazdırma Microsoft Foundation Class Kitaplığı (MFC) nasıl uygulandığını ve nasıl yararlanabileceğinizi altyapısına zaten oluşturulmuş yazdırma mimarisi açıklanmaktadır. Makaleler de MFC kolay uygulama baskı önizlemeyi işlevselliğinin nasıl desteklediğini ve nasıl kullanın ve bu işlevselliğini değiştirmenize açıklamaktadır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Yazdırma](../mfc/printing.md)

- [Baskı Önizleme mimarisi](../mfc/print-preview-architecture.md)

- [Örnek](../visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
