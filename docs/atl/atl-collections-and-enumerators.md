---
title: "ATL koleksiyonları ve numaralandırmalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4738e3f5256fe654dd64541dfd021ba2b4fce090
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-collections-and-enumerators"></a>ATL Koleksiyonları ve Numaralandırmalar
A `collection` veri öğelerinin (Ham verileri veya diğer nesnelerin) grubuna erişim sağlayan bir arabirim sağlayan bir COM nesnesidir. Bir grup erişimi sağlama olarak bilinen için standartlarını takip eden bir arabirim bir *koleksiyonu arabirimi*.  
  
 En azından, koleksiyon arabirimleri sağlamalısınız bir **sayısı** koleksiyondaki öğe sayısını döndürür özelliği bir **öğesi** dayalı bir dizin, koleksiyondaki bir öğe döndüren özelliği ve `_NewEnum` özellik koleksiyonu için bir numaralandırıcı döndürür. İsteğe bağlı olarak, koleksiyon arabirimleri sağlayabilir **Ekle** ve **kaldırmak** eklenen veya koleksiyondan silinen öğeleri izin veren yöntemleri ve **Temizle** kaldırmak için yöntemi tüm öğeler.  
  
 Bir `enumerator` bir koleksiyondaki öğelerin üzerinden yineleme için bir arabirim sağlayan bir COM nesnesidir. Numaralandırıcı arabirimleri dört gerekli yöntem aracılığıyla bir koleksiyonun öğelerini seri erişim sağlar: `Next`, **atla**, **sıfırlama**, ve `Clone`.  
  
 Okumayı archetypal (ancak tamamen sanal) tarafından Numaralandırıcı arabirimleri hakkında daha fazla bilgiyi [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx) arabirimi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [ATL koleksiyon ve Numaralandırıcı sınıfları](../atl/atl-collection-and-enumerator-classes.md)  
 Kısaca açıklayan ve Koleksiyonlar ve numaralandırmalar yardımcı olacak ATL sınıfları bağlantılar uygulamak sağlar.  
  
 [Tasarım ilkeleri toplama ve Numaralandırıcı arabirimleri](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Her tür arabirimi arkasında farklı tasarım ilkeleri açıklanır.  
  
 [C++ Standart Kitaplığı tabanlı bir koleksiyon uygulama](../atl/implementing-an-stl-based-collection.md)  
 C++ Standart Kitaplığı tabanlı bir koleksiyon uygulama anlatan genişletilmiş örneği.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Etkin Şablon Kütüphanesi kullanarak programı kavramsal konulara bağlantılar verilmektedir.  
  
 [ATLCollections örnek](../visual-cpp-samples.md)  
 Kullanımını gösteren bir örnek `ICollectionOnSTLImpl` ve `CComEnumOnSTL`ve özel kopyalama İlkesi sınıfları uygulamasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

