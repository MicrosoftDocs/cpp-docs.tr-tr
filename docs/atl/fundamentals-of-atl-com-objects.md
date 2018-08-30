---
title: ATL COM nesnelerinin temelleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9dc87340d567f876d91abc4d8ebfa1d6353cad
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209993"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM nesnelerinin temelleri
ATL COM nesnesini tanımlamak için kullanılan arabirimler ve sınıflar arasındaki ilişkiyi aşağıdaki çizimde gösterilmektedir.  
  
 ![ATL yapısı](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  Bu diyagramda gösterilmektedir `CComObject` türetilir `CYourClass` ise `CComAggObject` ve `CComPolyObject` dahil `CYourClass` bir üye değişkeni.  
  
 ATL COM nesnesini tanımlamak için üç yolu vardır. Standart seçeneğini kullanmaktır `CComObject` sınıfından türetilen sınıf `CYourClass`. İkinci seçenek kullanılarak toplanan nesne oluşturma, `CComAggObject` sınıfı. Üçüncü seçenek kullanmaktır `CComPolyObject` sınıfı. `CComPolyObject` karma davranır: olarak işlev görebilir bir `CComObject` sınıfı veya farklı bir `CComAggObject` nasıl ilk oluşturulduğuna bağlı olarak sınıfı. Nasıl kullanılacağı hakkında daha fazla bilgi için `CComPolyObject` sınıfı [CComPolyObject sınıfı](../atl/reference/ccompolyobject-class.md).  
  
 Standart ATL COM kullandığınızda, iki nesne kullanın: dış bir nesne ve bir iç nesne. Dış istemcilere işlevselliğini iç nesne dış nesne içinde tanımlanan sarmalayıcı işlevleri aracılığıyla erişin. Dış nesne türünde `CComObject`.  
  
 Toplanan nesne kullandığınızda, dış nesne sarmalayıcıları için iç nesneyi işlevselliğini sağlamaz. Bunun yerine, dış nesne, dış istemciler tarafından doğrudan erişilebilen bir işaretçi sağlar. Bu senaryoda dış nesne türünde `CComAggObject`. İç nesne dış nesne üyesi değişkeninin ve türü `CYourClass`.  
  
 İstemci iç nesneyi ile etkileşim kurmak için dış nesne aracılığıyla Git sahip olmadığından, toplu genellikle daha verimli nesneleridir. Ayrıca, toplu nesnenin arabirimi istemciye doğrudan kullanılabilir olması koşuluyla, toplanan nesnesinin işlevselliğini bilmek dış nesne yok. Ancak, tüm nesneleri toplanabilir. Toplanacak bir nesne için bunu aklınızda toplama ile tasarlanmış olması gerekir.  
  
 ATL uygulayan [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) iki aşama içinde:  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), veya [CComPolyObject](../atl/reference/ccompolyobject-class.md) uygulayan `IUnknown` yöntemleri.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) dış işaretçileri ve başvuru sayısını yönetir `IUnknown`.  
  
 ATL COM nesnenizin diğer yönleri diğer sınıfları tarafından işlenir:  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) nesnenin varsayılan sınıf üreteci ve toplama modelini tanımlar.  
  
-   [Idispatchımpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamayı sağlar `IDispatch Interface` nesne üzerinde herhangi bir ikili arabirimler kısmı.  
  
-   [Isupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) uygulayan `ISupportErrorInfo` hata bilgilerini sağlar arabirimi yayılan çağrı zincirini doğru.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [CComObjectRootEx Uygulama](../atl/implementing-ccomobjectrootex.md)  
 Örnek uygulama için COM eşleme girişleri show `CComObjectRootEx`.  
  
 [CComObject, CComAggObject ve CComPolyObject Uygulama](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Açıklar nasıl **DECLARE_\*_AGGREGATABLE** makroları kullanımını etkileyen `CComObject`, `CComAggObject`, ve `CComPolyObject`.  
  
 [IDispatch ve IErrorInfo Destekleme](../atl/supporting-idispatch-and-ierrorinfo.md)  
 ATL uygulama sınıfları desteklemek için kullanılacak listeler `IDispatch` ve `IErrorInfo` arabirimleri.  
  
 [IDispEventImpl Destekleme](../atl/supporting-idispeventimpl.md)  
 Sınıfınız için bir bağlantı noktası uygulanacak adımlar açıklanmaktadır.  
  
 [Varsayılan Sınıf Üreteci ve Toplama Modelini Değiştirme](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Varsayılan sınıf üreteci ve toplama modelini değiştirme için kullanılacak hangi makroları gösterir.  
  
 [Toplanan Nesne oluşturma](../atl/creating-an-aggregated-object.md)  
 Toplanan nesne oluşturma adımları listelenir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATL Projesi Oluşturma](../atl/reference/creating-an-atl-project.md)  
 ATL COM Nesne oluşturma hakkında bilgi sağlar.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

