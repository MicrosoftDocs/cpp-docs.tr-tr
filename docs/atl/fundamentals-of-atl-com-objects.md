---
description: 'Daha fazla bilgi edinin: ATL COM nesnelerinin temelleri'
title: ATL COM nesnelerinin temelleri
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 0a94d57701770b00eb2c2d5aed675b8cc19e9e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152943"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM nesnelerinin temelleri

Aşağıdaki çizimde, ATL COM nesnesini tanımlamak için kullanılan sınıflar ve arabirimler arasındaki ilişki gösterilmektedir.

![ATL yapısı](../atl/media/vc307y1.gif "ATL yapısı")

> [!NOTE]
> Bu diyagram `CComObject` , ' den türetilen `CYourClass` `CComAggObject` ve `CComPolyObject` üye değişkeni olarak dahil olan ' i gösterir `CYourClass` .

ATL COM nesnesi tanımlamanın üç yolu vardır. Standart seçeneği, `CComObject` öğesinden türetilen sınıfı kullanmaktır `CYourClass` . İkinci seçenek, sınıfını kullanarak toplanmış bir nesne oluşturmaktır `CComAggObject` . Üçüncü seçenek `CComPolyObject` sınıfını kullanmaktır. `CComPolyObject` karma işlevi görür: `CComObject` `CComAggObject` ilk oluşturulma şekline bağlı olarak bir sınıf veya sınıf olarak çalışabilir. Sınıfının nasıl kullanılacağı hakkında daha fazla bilgi için `CComPolyObject` bkz. [CComPolyObject sınıfı](../atl/reference/ccompolyobject-class.md).

Standart ATL COM kullandığınızda iki nesne kullanırsınız: bir dış nesne ve bir iç nesne. Dış istemciler, dış nesnede tanımlanan sarmalayıcı işlevleri aracılığıyla iç nesne işlevlerine erişir. Dış nesne türündedir `CComObject` .

Toplanmış bir nesne kullandığınızda, dış nesne iç nesnenin işlevselliği için sarmalayıcılar sağlamaz. Bunun yerine, dış nesne doğrudan dış istemciler tarafından erişilen bir işaretçi sağlar. Bu senaryoda, dış nesne türündedir `CComAggObject` . İç nesne, dış nesnenin üye değişkenidir ve türüdür `CYourClass` .

İstemci, iç nesneyle etkileşimde bulunmak için dış nesneden gezinmek zorunda olmadığından, toplanmış nesneler genellikle daha etkilidir. Ayrıca, toplanan nesnenin arabirimi doğrudan istemci tarafından kullanılabilir olduğu için, dış nesne, toplanmış nesnenin işlevselliğini bilmelidir. Ancak, tüm nesneler toplanamaz. Toplanacak bir nesne için, dikkat etmeniz gereken toplama ile tasarlanmalıdır.

ATL, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'yi iki aşamada uygular:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md)veya [CComPolyObject](../atl/reference/ccompolyobject-class.md) `IUnknown` yöntemleri uygular.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) , başvuru sayısını ve dış işaretçilerini yönetir `IUnknown` .

ATL COM nesnenizin diğer yönleri diğer sınıflar tarafından işlenir:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) , nesnenin varsayılan sınıf fabrikası ve toplama modelini tanımlar.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) `IDispatch Interface` nesne üzerindeki herhangi bir çift arabirimin bölümünün varsayılan bir uygulamasını sağlar.

- [Iupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) , `ISupportErrorInfo` hata bilgilerinin çağrı zincirini doğru şekilde yayılmasını sağlayan arabirimi uygular.

## <a name="in-this-section"></a>Bu Bölümde

[CComObjectRootEx uygulama](../atl/implementing-ccomobjectrootex.md)<br/>
Uygulamak için örnek COM eşleme girdilerini gösterir `CComObjectRootEx` .

[CComObject, CComAggObject ve CComPolyObject uygulama](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
**DECLARE_ \* _AGGREGATABLE** makroların,, ve kullanımını nasıl etkilediğini açıklar `CComObject` `CComAggObject` `CComPolyObject` .

[IDispatch ve IErrorInfo desteği](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
Ve arabirimlerini desteklemek için kullanılacak ATL uygulama sınıflarını listeler `IDispatch` `IErrorInfo` .

[IDispEventImpl desteği](../atl/supporting-idispeventimpl.md)<br/>
Sınıfınız için bir bağlantı noktası uygulamak için gereken adımları açıklar.

[Varsayılan sınıf fabrikası ve toplama modelini değiştirme](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Varsayılan sınıf fabrikası ve toplama modelini değiştirmek için kullanılacak makroları görüntüleyin.

[Toplanmış nesne oluşturma](../atl/creating-an-aggregated-object.md)<br/>
Toplu bir nesne oluşturmak için gereken adımları listeler.

## <a name="related-sections"></a>İlgili Bölümler

[ATL Projesi Oluşturma](../atl/reference/creating-an-atl-project.md)<br/>
ATL COM nesnesi oluşturma hakkında bilgi sağlar.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
