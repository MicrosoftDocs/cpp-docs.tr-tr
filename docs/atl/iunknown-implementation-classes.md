---
title: "IUnknown uygulaması sınıfları (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.Iunknown
dev_langs: C++
helpviewer_keywords: IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ac484e58b585a09eff40d1b058e44dad6b8d394c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iunknown-implementation-classes"></a>IUnknown uygulaması sınıfları
Aşağıdaki sınıflar uygulama **IUnknown** ve ilgili yöntemler:  
  
-   [İn uygulamasına](../atl/reference/ccomobjectrootex-class.md) başvuru toplanmış ve toplanmayan nesneler için sayım yönetir. İş parçacığı modelini belirtmenize olanak tanır.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) başvuru toplanmış ve toplanmayan nesneler için sayım yönetir. İş parçacığı modeli sunucusunun varsayılan kullanır.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) uygulayan **IUnknown** toplanmış bir nesne için.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) uygulayan **IUnknown** toplanmayan bir nesne.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) uygulayan **IUnknown** toplanmış ve toplanmayan nesneler için. Kullanarak `CComPolyObject` her ikisi de belirlemeyi önler `CComAggObject` ve `CComObject` , modülü. Tek bir `CComPolyObject` nesne toplanmış ve toplanmayan durumları işler.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) uygulayan **IUnknown** modül kilit sayısı değiştirmeden toplanmayan bir nesne.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) uygulayan **IUnknown** etiketleri arabirimi için.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) uygulayan **IUnknown** "önbelleğe alınan" etiketleri arabirimi için.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) uygulayan **IUnknown** iç nesne bir toplama veya etiketleri arabirimi.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) başvuru sayısı nesnenizin emin olmak için modül olmaz silinmesi yönetir.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) iskelet uyarlamasını kullanarak geçici bir COM nesnesi oluşturur **IUnknown**.  
  
## <a name="related-articles"></a>İlgili Makaleler  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../atl/atl-class-overview.md)   
 [Toplama ve sınıf Fabrika makroları](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM eşleme makroları](../atl/reference/com-map-macros.md)   
 [COM eşlemesi genel işlevler](../atl/reference/com-map-global-functions.md)

