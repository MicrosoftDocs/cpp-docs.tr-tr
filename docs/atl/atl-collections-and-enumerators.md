---
title: ATL Koleksiyonları ve Numaralandırmalar
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 502bedb1773dc2a6edbd6679d50e9c5946228283
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491897"
---
# <a name="atl-collections-and-enumerators"></a>ATL Koleksiyonları ve Numaralandırmalar

`collection` , Bir veri öğeleri grubuna (ham veriler veya diğer nesneler) erişim sağlayan bir arabirim sağlayan com nesnesidir. Bir nesne grubuna erişim sağlamaya yönelik standartları izleyen bir arabirim, *Koleksiyon arabirimi*olarak bilinir.

Koleksiyon arabirimlerinin en azından koleksiyondaki öğelerin sayısını `Count` `Item` , bir dizine göre koleksiyondan bir öğe döndüren bir özelliği ve `_NewEnum` bir özelliği döndüren bir özelliğini döndüren bir özellik sağlaması gerekir. koleksiyon için Numaralandırıcı. İsteğe bağlı olarak, koleksiyon arabirimleri `Add` , `Remove` öğelerin koleksiyona eklenmesine veya silinmesine izin vermek için yöntemler ve tüm öğeleri kaldırmak için bir `Clear` yöntem sağlar.

`enumerator` , Bir koleksiyondaki öğeler arasında yineleme için bir arabirim sağlayan com nesnesidir. Numaralandırıcı arabirimleri, bir koleksiyonun öğelerine seri erişim sağlayan `Next`dört gerekli Yöntem: `Skip` `Reset`,, ve `Clone`.

[IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) arabirimi gibi başvuru içeriğini okuyarak Numaralandırıcı arabirimleri hakkında daha fazla bilgi edinebilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

[ATL Koleksiyonu ve Numaralandırıcısı Sınıfları](../atl/atl-collection-and-enumerator-classes.md)<br/>
, Koleksiyonları ve numaralandırıcıları uygulamanıza yardımcı olacak ATL sınıflarının bağlantılarını kısaca açıklar.

[Koleksiyon ve Numaralandırıcı Arabirimleri için Tasarım İlkeleri](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
Her bir arabirim türünün arkasındaki farklı tasarım ilkelerini açıklar.

[C++ Standart Kitaplığı Temelli Koleksiyon Uygulama](../atl/implementing-an-stl-based-collection.md)<br/>
Standart Kitaplık tabanlı bir C++ koleksiyonun uygulamasında size kılavuzluk eden genişletilmiş bir örnek.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.

[ATLCollections örneği](../overview/visual-cpp-samples.md)<br/>
`ICollectionOnSTLImpl` Ve`CComEnumOnSTL`' nin kullanımını ve özel kopyalama ilkesi sınıflarının uygulanmasını gösteren bir örnek.

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../atl/active-template-library-atl-concepts.md)
