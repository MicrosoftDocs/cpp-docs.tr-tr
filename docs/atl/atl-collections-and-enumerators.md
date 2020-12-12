---
description: 'Daha fazla bilgi edinin: ATL koleksiyonları ve Numaralandırıcılar'
title: ATL Koleksiyonları ve Numaralandırmalar
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 92e9ab3df52219812d72ae5cb811f57a3ecf4fad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166011"
---
# <a name="atl-collections-and-enumerators"></a>ATL Koleksiyonları ve Numaralandırmalar

`collection`, Bir veri öğeleri grubuna (ham veriler veya diğer nesneler) erişim sağlayan bir arabirim sağlayan com nesnesidir. Bir nesne grubuna erişim sağlamaya yönelik standartları izleyen bir arabirim, *Koleksiyon arabirimi* olarak bilinir.

Koleksiyon arabirimlerinin en azından koleksiyondaki `Count` öğelerin sayısını, `Item` bir dizini temel alan koleksiyondan bir öğe döndüren bir özelliği ve `_NewEnum` koleksiyon için bir Numaralandırıcı döndüren bir özelliği sağlaması gerekir. İsteğe bağlı olarak, koleksiyon arabirimleri `Add` , `Remove` öğelerin koleksiyona eklenmesine veya silinmesine izin vermek için yöntemler ve `Clear` tüm öğeleri kaldırmak için bir yöntem sağlar.

`enumerator`, Bir koleksiyondaki öğeler arasında yineleme için bir arabirim sağlayan com nesnesidir. Numaralandırıcı arabirimleri, bir koleksiyonun öğelerine seri erişim sağlayan dört gerekli Yöntem:,, `Next` `Skip` `Reset` ve `Clone` .

[IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) arabirimi gibi başvuru içeriğini okuyarak Numaralandırıcı arabirimleri hakkında daha fazla bilgi edinebilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

[ATL koleksiyonu ve Numaralandırıcı sınıfları](../atl/atl-collection-and-enumerator-classes.md)<br/>
, Koleksiyonları ve numaralandırıcıları uygulamanıza yardımcı olacak ATL sınıflarının bağlantılarını kısaca açıklar.

[Koleksiyon ve Numaralandırıcı arabirimleri için tasarım Ilkeleri](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
Her bir arabirim türünün arkasındaki farklı tasarım ilkelerini açıklar.

[C++ standart Library-Based koleksiyonu uygulama](../atl/implementing-an-stl-based-collection.md)<br/>
C++ standart kitaplığı tabanlı bir koleksiyonun uygulamasında size kılavuzluk eden genişletilmiş bir örnek.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.

[ATLCollections örneği](../overview/visual-cpp-samples.md)<br/>
Ve ' nin kullanımını ve `ICollectionOnSTLImpl` `CComEnumOnSTL` özel kopyalama ilkesi sınıflarının uygulanmasını gösteren bir örnek.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
