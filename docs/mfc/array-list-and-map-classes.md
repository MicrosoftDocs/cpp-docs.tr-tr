---
title: Dizi, Liste ve Eşleme Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
ms.openlocfilehash: b89b99abb79fe689274f9e0b89a85bb33643d324
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274381"
---
# <a name="array-list-and-map-classes"></a>Dizi, Liste ve Eşleme Sınıfları

Toplamalar veri işleme için sınıf kitaplığının bir grup koleksiyon sınıfları sağlar — diziler, listeler ve eşler — nesne ve türleri önceden tanımlanmış çeşitli tutabilir. Koleksiyonları dinamik olarak boyutlandırılır. Bu sınıflar, herhangi bir programda için Windows veya yazılmış kullanılabilir. Ancak, bunlar uygulama çerçevesi içinde belge sınıfları tanımlayan veri yapıları uygulamak için en kullanışlıdır. Kolayca özel koleksiyon sınıfları bu türetebilirsiniz veya bunları şablon sınıflarını temel oluşturabilirsiniz. Bu yaklaşımlar hakkında daha fazla bilgi için bkz [koleksiyonları](../mfc/collections.md). Şablon koleksiyon sınıfları listesi için bkz [diziler, listeler ve eşlemeler için şablon sınıfları](../mfc/template-classes-for-arrays-lists-and-maps.md).

Bellekte bitişik depolanır tek boyutlu veri yapılarını dizilerdir. Belirli bir öğenin bellek adresi öğenin dizini öğenin boyutuna çarparak ve sonucu bir dizi temel adrese ekleme hesaplanabilir olduğundan çok hızlı rastgele erişim destekledikleri. Ancak, diziye öğe eklemek varsa, son tüm dizi beri eklenen eklenecek öğe için yer açmak üzere taşınması öğesinin çok pahalı dizilerdir. Diziler, büyütme ve küçültme gerektiğinde.

Listeler, diziler için benzer, ancak çok farklı şekilde depolanır. Listedeki her öğeye bir işaretçi karakteriyle bağlı bir liste yapmadan önceki ve sonraki öğeleri de içerir. Ekleme veya Bunun yapılması yalnızca birkaç işaretçileri değiştirme içerdiğinden öğeleri silme çok hızlıdır. Tüm aramalar listenin uçları birini başlatın olması gerektiğinden ancak arama listesini pahalı olabilir.

Haritalar için veri değeri bir anahtar değeri ilgilidir. Örneğin, bir harita anahtarı bir dize ve verileri bir listesine bir işaretçi olabilir. Belirli bir dize ile ilişkili işaretçi size harita sorduğu. Harita aramaları hızlı olduğu anahtar aramaları için karma tablo eşlemeleri kullanın. Ayrıca öğelerini eklemeyi ve silmeyi hızlı çalışır. Haritalar, genellikle ikincil dizinler diğer veri yapılarını ile kullanılır. MFC kullanan harita olarak adlandırılan özel bir tür bir [ileti eşlemesi](../mfc/mapping-messages.md) Windows iletileri için bu ileti işleyici işlevine bir işaretçi eşlemek için.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
