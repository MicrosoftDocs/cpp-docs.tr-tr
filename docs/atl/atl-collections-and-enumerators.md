---
title: ATL koleksiyonları ve numaralandırıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00265d3ce0f8ea867021500777d93991d245be47
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204819"
---
# <a name="atl-collections-and-enumerators"></a>ATL Koleksiyonları ve Numaralandırmalar
A `collection` veri öğelerinin (Ham verileri veya diğer nesneleri) bir gruba erişim sağlayan bir arabirim sunan bir COM nesnesi olması. Bir grup nesne erişimi sağlama olarak da bilinen için standartlarını takip eden bir arabirim bir *koleksiyon arabirimi*.  
  
 En azından, koleksiyon arabirimleri sağlamalısınız bir `Count` koleksiyondaki öğe sayısını döndüren özellik bir `Item` bir dizinini temel alarak koleksiyondan bir öğe döndüren özellik ve `_NewEnum` döndüren özellik bir koleksiyon için Numaralandırıcı. İsteğe bağlı olarak, koleksiyon arabirimleri sağlayabilir `Add` ve `Remove` eklenen veya koleksiyondan silinen öğeleri izin veren yöntemleri ve `Clear` tüm öğeleri kaldırmak için yöntemi.  
  
 Bir `enumerator` bir koleksiyondaki öğelerin üzerinden yineleme için bir arabirim sunan bir COM nesnesi. Numaralandırıcı arabirimleri dört gerekli yöntemleri aracılığıyla bir koleksiyonun öğeleri seri erişim sağlar: `Next`, `Skip`, `Reset`, ve `Clone`.  
  
 Numaralandırıcı arabirimleri okuyarak hakkında daha fazla başvuru içeriği aşağıdaki gibi edinebilirsiniz [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) arabirimi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [ATL Koleksiyonu ve Numaralandırıcısı Sınıfları](../atl/atl-collection-and-enumerator-classes.md)  
 Kısaca açıklayan ve koleksiyonları ve numaralandırıcıları yardımcı olacak ATL sınıfları için bağlantıları uygulama sağlar.  
  
 [Koleksiyon ve Numaralandırıcı Arabirimleri için Tasarım İlkeleri](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Her tür arabirimin arkasına farklı tasarım ilkelerini ele alınmaktadır.  
  
 [C++ Standart Kitaplığı Temelli Koleksiyon Uygulama](../atl/implementing-an-stl-based-collection.md)  
 Bir C++ Standart Kitaplığı temelli koleksiyon uygulama size genişletilmiş bir örnek.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.  
  
 [ATLCollections örnek](../visual-cpp-samples.md)  
 Kullanımını gösteren bir örnek `ICollectionOnSTLImpl` ve `CComEnumOnSTL`ve özel kopyalama İlkesi sınıfları uygulamasını.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

