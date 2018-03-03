---
title: ATL COM nesneleri temelleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5a43af31a88420c154d7a57d27d2b69787d11d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM nesneleri temelleri
Aşağıdaki çizim sınıfları ve ATL COM nesneyi tanımlamak için kullanılan arabirimleri arasındaki ilişkiyi gösterir.  
  
 ![ATL yapısı](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  Bu diyagramda gösterilmektedir `CComObject` türetildiği `CYourClass` ancak `CComAggObject` ve `CComPolyObject` dahil `CYourClass` üye değişkeni olarak.  
  
 ATL COM nesneyi tanımlamak için üç yolu vardır. Standart seçeneği kullanmaktır `CComObject` sınıfından türetilmiş sınıf `CYourClass`. İkinci seçenek kullanılarak toplanan nesne oluşturmak, `CComAggObject` sınıfı. Üçüncü seçenek kullanmaktır `CComPolyObject` sınıfı. `CComPolyObject`bir karma davranır: olarak çalışabilmesi için bir `CComObject` sınıfı veya farklı bir `CComAggObject` nasıl ilk oluşturulduğuna bağlı olarak sınıfı. Nasıl kullanılacağı hakkında daha fazla bilgi için `CComPolyObject` sınıfı için bkz: [CComPolyObject sınıfı](../atl/reference/ccompolyobject-class.md).  
  
 Standart ATL COM kullandığınızda, iki nesne kullanın: Dış nesne ve bir iç nesne. Dış istemcilere iç nesneyi işlevselliğini dış nesnesinde tanımlanan sarmalayıcı işlevleri aracılığıyla erişin. Dış nesne türünde `CComObject`.  
  
 Toplanan nesneyi kullandığınızda, dış nesne iç nesneyi işlevselliği için sarmalayıcıları sağlamaz. Bunun yerine, dış nesne doğrudan dış istemcileri tarafından erişilebilen bir işaretçi sağlar. Bu senaryoda, dış nesne türüdür `CComAggObject`. İç nesneyi bir dış nesnenin üye değişkendir ve türü `CYourClass`.  
  
 İstemci iç nesne ile etkileşim kurmak için dış nesne gitmesi sahip olmadığından, toplanan genellikle daha verimli nesneleridir. Ayrıca, toplanan nesne arabiriminin istemciye doğrudan kullanılabilir olması koşuluyla, toplanan nesnesinin işlevselliğini bilmeniz dış nesne yok. Ancak, tüm nesneleri kümelenebilir. Bir nesne toplanacak aklınızda toplama ile tasarlanması gerekir.  
  
 ATL uygulayan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) iki aşamaya içinde:  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), veya [CComPolyObject](../atl/reference/ccompolyobject-class.md) uygulayan **IUnknown** yöntemleri.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) veya [in uygulamasına](../atl/reference/ccomobjectrootex-class.md) başvuru sayısı ve dış işaretçileri yönetir **IUnknown**.  
  
 ATL COM nesnesi diğer yönlerini diğer sınıflar tarafından ele alınmıştır:  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) nesnenin, varsayılan sınıf Fabrika ve toplama modeli tanımlar.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamayı sağlar `IDispatch Interface` çift arabirimlerden nesnesindeki kısmı.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) uygulayan **ISupportErrorInfo** hata bilgilerini sağlar arabirimi yayılan araması zincirinde doğru.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [CComObjectRootEx Uygulama](../atl/implementing-ccomobjectrootex.md)  
 Örnek COM eşleme girdilerini uygulamak için show `CComObjectRootEx`.  
  
 [CComObject, CComAggObject ve CComPolyObject Uygulama](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Anlatılmaktadır nasıl **DECLARE_\*_AGGREGATABLE** makroları kullanımını etkileyen `CComObject`, `CComAggObject`, ve `CComPolyObject`.  
  
 [IDispatch ve IErrorInfo Destekleme](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Desteklemek için kullanılacak ATL uygulama sınıfları listeler `IDispatch` ve **IErrorInfo** arabirimleri.  
  
 [IDispEventImpl Destekleme](../atl/supporting-idispeventimpl.md)  
 Bir bağlantı noktası, sınıf için uygulanacak adımlar açıklanmaktadır.  
  
 [Varsayılan Sınıf Üreteci ve Toplama Modelini Değiştirme](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Varsayılan sınıf Fabrika ve toplama modeli değiştirmek üzere kullanmak için hangi makroları gösterir.  
  
 [Toplanan Nesne oluşturma](../atl/creating-an-aggregated-object.md)  
 Toplanan nesne oluşturma adımlarını listeler.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATL Projesi Oluşturma](../atl/reference/creating-an-atl-project.md)  
 ATL COM Nesne oluşturma hakkında bilgi sağlar.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Etkin Şablon Kütüphanesi kullanarak programı kavramsal konulara bağlantılar verilmektedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

