---
title: IUnknown uygulaması sınıfları (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d67b2a7b9769acd7d6e596e4fcdf1aec30bbf74
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357222"
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
 [ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../atl/atl-class-overview.md)   
 [Toplama ve sınıf Fabrika makroları](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM eşleme makroları](../atl/reference/com-map-macros.md)   
 [COM Eşlemesi Genel İşlevleri](../atl/reference/com-map-global-functions.md)

