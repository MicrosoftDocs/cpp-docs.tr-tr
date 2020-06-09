---
title: Dizi, Liste ve Eşleme Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
ms.openlocfilehash: 9583d8263901c4a135a3ba1f560856b2a8915168
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626101"
---
# <a name="array-list-and-map-classes"></a>Dizi, Liste ve Eşleme Sınıfları

Veri toplamlarını işlemek için, sınıf kitaplığı çeşitli nesne ve önceden tanımlanmış türler içerebilen bir grup koleksiyon sınıfı (diziler, listeler ve haritalar) sağlar. Koleksiyonlar dinamik olarak boyutlandırılır. Bu sınıflar, Windows için yazılmış olup olmadığı herhangi bir programda kullanılabilir. Ancak, uygulama çerçevesindeki belge sınıflarınızı tanımlayan veri yapılarını uygulamak için en yararlı seçenektir. Özel koleksiyon sınıflarını bunlardan kolayca türetebilirsiniz veya onları şablon sınıflarına göre oluşturabilirsiniz. Bu yaklaşımlar hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](collections.md). Şablon koleksiyonu sınıflarının bir listesi için, [diziler, listeler ve haritalar Için şablon sınıfları](template-classes-for-arrays-lists-and-maps.md)makalesine bakın.

Diziler bellekte bitişik olarak depolanan tek boyutlu veri yapılarıdır. Belirli bir öğenin bellek adresi, öğenin dizini bir öğe boyutuna çarpılarak hesaplanabileceğinden ve sonuç dizinin temel adresine eklenerek hesaplanabileceğinden, çok hızlı rastgele erişimi destekler. Ancak öğeleri diziye eklemek istiyorsanız diziler çok pahalı olur, çünkü eklenen öğeden önceki tüm dizi, eklenecek öğe için yer açmak üzere taşınmalıdır. Diziler gerektiğinde büyüyebilir ve küçülebilir.

Listeler dizilere benzerdir, ancak çok farklı bir şekilde depolanır. Bir listedeki her öğe, önceki ve sonraki öğelere yönelik bir işaretçi de içerir ve bu da, bunu, birbirine bağlı bir liste haline getirir. Yalnızca birkaç işaretçilerin değiştirilmesini içerdiğinden öğe eklemek veya silmek çok hızlıdır. Ancak, listenin uçlarından birinde tüm aramaların başlaması gerektiğinden, bir listeyi aramak pahalı olabilir.

Haritalar bir anahtar değerini bir veri değeriyle ilişkilendirir. Örneğin, bir haritanın anahtarı bir dize ve bir liste işaretçisi olan veri olabilir. Haritanın size belirli bir dizeyle ilişkili olan işaretçiyi vermesini isteyebilirsiniz. Haritalar, anahtar aramaları için karma tablolar kullandığından, harita aramaları hızlıdır. Öğe ekleme ve silme de hızlıdır. Haritalar genellikle diğer veri yapıları ile yardımcı dizin olarak kullanılır. MFC, Windows iletilerini bu ileti için işleyici işlevine yönelik bir işaretçiye eşlemek için [ileti eşlemesi](mapping-messages.md) adlı özel bir tür eşleme kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
