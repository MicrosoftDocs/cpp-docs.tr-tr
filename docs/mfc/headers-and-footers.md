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
ms.openlocfilehash: 7024c57dbe41a579582d409d0536db0ca0bc46d6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620103"
---
# <a name="headers-and-footers"></a>Üstbilgiler ve Altbilgiler

Bu makalede, yazdırılan bir belgeye üst bilgilerin ve altbilgilerin nasıl ekleneceği açıklanmaktadır.

Ekrandaki bir belgeye baktığınızda, belgenin adı ve belgedeki geçerli konumunuz genellikle başlık çubuğunda ve durum çubuğunda görüntülenir. Belgenin yazdırılmış bir kopyasına baktığınızda, bir üst bilgi veya alt bilgide gösterilen ad ve sayfa numarası olması yararlı olur. Bu, hatta WYSıWYG programlarının yazdırma ve ekran görüntüleme gerçekleştirdiklerinde farklılık gösterdiği yaygın bir yoldur.

[OnPrint](reference/cview-class.md#onprint) üye işlevi, her sayfa için çağrıldığı ve yalnızca yazdırma için çağrılmakta olduğu için, ekran görüntüsü için değil, üst bilgileri veya altbilgileri yazdırmak için uygun bir yerdir. Üst bilgi veya alt bilgi yazdırmak için ayrı bir işlev tanımlayabilir ve yazıcı cihazı bağlamını ' den geçirebilirsiniz `OnPrint` . Sayfa gövdesinin üst bilgi veya altbilgiyle örtüşmesini önlemek için [OnDraw](reference/cview-class.md#ondraw) çağrılmadan önce pencere kaynağını veya kapsamını ayarlamanız gerekebilir. Ayrıca, `OnDraw` sayfaya sığan belge miktarı azaltılamadığından değiştirmeniz gerekebilir.

Üst bilgi veya alt bilgi tarafından alınan alanı telafi etmenin bir yolu, [CPrintInfo](reference/cprintinfo-structure.md) **m_rectDraw** üyesini kullanmaktır. Sayfanın her yazdırılışında, bu üye sayfanın kullanılabilir alanıyla başlatılır. Sayfanın gövdesini yazdırmadan önce bir üst bilgi veya alt bilgi yazdırırsanız, üst bilgi veya alt bilgi tarafından alınan alana **m_rectDraw** için depolanan dikdörtgenin boyutunu azaltabilirsiniz. Ardından `OnPrint` , sayfanın gövdesini yazdırmak için ne kadar alan kaldığını öğrenmek için **m_rectDraw** 'ye başvurabilirsiniz.

[Onhazırlık EDC](reference/cview-class.md#onpreparedc)'den bir üst bilgiyi ya da başka bir şeyi yazdıramazsınız çünkü `StartPage` [CDC](reference/cdc-class.md) üye işlevi çağrılmadan önce çağrılır. Bu noktada, yazıcı cihaz bağlamı sayfa sınırında olduğu kabul edilir. Yalnızca `OnPrint` üye işlevden yazdırma yapabilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Çok sayfalı belgeleri yazdırma](multipage-documents.md)

- [Yazdırma için GDI kaynaklarını ayırma](allocating-gdi-resources.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yazdırma](printing.md)
