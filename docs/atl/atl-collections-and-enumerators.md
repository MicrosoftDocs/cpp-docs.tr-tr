---
title: ATL Koleksiyonları ve Numaralandırmalar
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: ebf7be8b2c80a714a27567ce0334475519a69454
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768022"
---
# <a name="atl-collections-and-enumerators"></a>ATL Koleksiyonları ve Numaralandırmalar

A `collection` veri öğelerinin (Ham verileri veya diğer nesneleri) bir gruba erişim sağlayan bir arabirim sunan bir COM nesnesi olması. Bir grup nesne erişimi sağlama olarak da bilinen için standartlarını takip eden bir arabirim bir *koleksiyon arabirimi*.

En azından, koleksiyon arabirimleri sağlamalısınız bir `Count` koleksiyondaki öğe sayısını döndüren özellik bir `Item` bir dizinini temel alarak koleksiyondan bir öğe döndüren özellik ve `_NewEnum` döndüren özellik bir koleksiyon için Numaralandırıcı. İsteğe bağlı olarak, koleksiyon arabirimleri sağlayabilir `Add` ve `Remove` eklenen veya koleksiyondan silinen öğeleri izin veren yöntemleri ve `Clear` tüm öğeleri kaldırmak için yöntemi.

Bir `enumerator` bir koleksiyondaki öğelerin üzerinden yineleme için bir arabirim sunan bir COM nesnesi. Numaralandırıcı arabirimleri dört gerekli yöntemleri aracılığıyla bir koleksiyonun öğeleri seri erişim sağlar: `Next`, `Skip`, `Reset`, ve `Clone`.

Numaralandırıcı arabirimleri okuyarak hakkında daha fazla başvuru içeriği aşağıdaki gibi edinebilirsiniz [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) arabirimi.

## <a name="in-this-section"></a>Bu Bölümde

[ATL Koleksiyonu ve Numaralandırıcısı Sınıfları](../atl/atl-collection-and-enumerator-classes.md)<br/>
Kısaca açıklayan ve koleksiyonları ve numaralandırıcıları yardımcı olacak ATL sınıfları için bağlantıları uygulama sağlar.

[Koleksiyon ve Numaralandırıcı Arabirimleri için Tasarım İlkeleri](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
Her tür arabirimin arkasına farklı tasarım ilkelerini ele alınmaktadır.

[C++ Standart Kitaplığı Temelli Koleksiyon Uygulama](../atl/implementing-an-stl-based-collection.md)<br/>
Bir C++ Standart Kitaplığı temelli koleksiyon uygulama size genişletilmiş bir örnek.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.

[ATLCollections örnek](../overview/visual-cpp-samples.md)<br/>
Kullanımını gösteren bir örnek `ICollectionOnSTLImpl` ve `CComEnumOnSTL`ve özel kopyalama İlkesi sınıfları uygulamasını.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)
