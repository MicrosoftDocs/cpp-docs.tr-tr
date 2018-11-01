---
title: Üstbilgiler ve Altbilgiler
ms.date: 11/04/2016
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
ms.openlocfilehash: 15c76dabb2512b5906ca631e0da5047fabddf848
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564508"
---
# <a name="headers-and-footers"></a>Üstbilgiler ve Altbilgiler

Bu makalede, üstbilgiler ve altbilgiler yazdırılmış bir belgeye ekleme açıklanmaktadır.

Ekranda bir belgeye baktığınızda, belge ve belgedeki konumunuzu adı genellikle görüntülenir başlık çubuğu ve durum çubuğu. Bir belgenin basılı kopya aranırken bir üstbilgisinde veya altbilgisinde gösterilen ad ve sayfa numarası kullanışlıdır. Bu, hangi bile WYSIWYG içinde nasıl yazdırma ve ekran görüntüsünü gerçekleştirdikleri içinde programlar farklı genel bir yoludur.

[OnPrint](../mfc/reference/cview-class.md#onprint) üye işlev, her sayfa için çağrıldığından ve ekran için değil, yazdırma işlemi için yalnızca çağrıldığından üstbilgilerinde veya altbilgilerinde yazdırmak için uygun bir yerde. Üstbilgisindeki veya altbilgisindeki yazdırmak için ayrı bir fonksiyon tanımlayın ve yazıcı cihaz bağlamdan geçirmek `OnPrint`. Pencere başlangıç nebo mez çağırmadan önce ayarlamanız gerekebilir [OnDraw](../mfc/reference/cview-class.md#ondraw) sayfa üstbilgisinde veya altbilgisinde çakışma gövdesi olmamasına özen gösterin. Değiştirmeniz gerekebilir `OnDraw` sayfasında uygun belge miktarını azaltılabilir olduğundan.

Üstbilginin veya altbilginin tarafından gerçekleştirilen alan kullanmak için dengelemek için tek yönlü **m_rectDraw** üyesi [Cprintınfo](../mfc/reference/cprintinfo-structure.md). Her zaman bir sayfa yazdırıldığında, bu üye sayfa kullanılabilir alanı ile başlatılır. Üstbilgisindeki veya altbilgisindeki sayfasının gövdesi yazdırmadan önce baskı, depolanan dikdörtgen boyutunu azaltabilirsiniz **m_rectDraw** üstbilgisindeki veya altbilgisindeki tarafından gerçekleştirilen alan hesaba. Ardından `OnPrint` başvurabilir **m_rectDraw** sayfasının gövdesi yazdırmak için ne kadar alan kalır kullanıma bulunacak.

Bir üst bilgi veya alanından başka bir şey yazdıramıyorum [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc), önce çağrıldığından `StartPage` üye işlevinin [CDC](../mfc/reference/cdc-class.md) çağrıldı. Bu noktada, yazıcı cihaz bağlamı bir sayfa sınırında olarak kabul edilir. Yazdırma yalnızca gerçekleştirebileceğiniz `OnPrint` üye işlevi.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Birden çok belge yazdırma](../mfc/multipage-documents.md)

- [Yazdırma için GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Yazdırma](../mfc/printing.md)

