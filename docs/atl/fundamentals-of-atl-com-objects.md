---
title: ATL COM nesnelerinin temelleri
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: ec83539b2d7101c534bbc1df33577df422e76152
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492363"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM nesnelerinin temelleri

Aşağıdaki çizimde, ATL COM nesnesini tanımlamak için kullanılan sınıflar ve arabirimler arasındaki ilişki gösterilmektedir.

![ATL yapısı](../atl/media/vc307y1.gif "ATL yapısı")

> [!NOTE]
>  Bu `CComObject` diyagram, '`CComAggObject` den `CYourClass` türetilen ve üye değişkeni `CComPolyObject` olarak `CYourClass` dahil olan ' i gösterir.

ATL COM nesnesi tanımlamanın üç yolu vardır. Standart seçeneği, öğesinden `CComObject` `CYourClass`türetilen sınıfı kullanmaktır. İkinci seçenek, `CComAggObject` sınıfını kullanarak toplanmış bir nesne oluşturmaktır. Üçüncü seçenek `CComPolyObject` sınıfını kullanmaktır. `CComPolyObject`karma işlevi görür: ilk oluşturulma şekline bağlı olarak bir `CComObject` sınıf veya `CComAggObject` sınıf olarak çalışabilir. `CComPolyObject` Sınıfının nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [CComPolyObject sınıfı](../atl/reference/ccompolyobject-class.md).

Standart ATL COM kullandığınızda iki nesne kullanırsınız: bir dış nesne ve bir iç nesne. Dış istemciler, dış nesnede tanımlanan sarmalayıcı işlevleri aracılığıyla iç nesne işlevlerine erişir. Dış nesne türündedir `CComObject`.

Toplanmış bir nesne kullandığınızda, dış nesne iç nesnenin işlevselliği için sarmalayıcılar sağlamaz. Bunun yerine, dış nesne doğrudan dış istemciler tarafından erişilen bir işaretçi sağlar. Bu senaryoda, dış nesne türündedir `CComAggObject`. İç nesne, dış nesnenin üye değişkenidir ve türüdür `CYourClass`.

İstemci, iç nesneyle etkileşimde bulunmak için dış nesneden gezinmek zorunda olmadığından, toplanmış nesneler genellikle daha etkilidir. Ayrıca, toplanan nesnenin arabirimi doğrudan istemci tarafından kullanılabilir olduğu için, dış nesne, toplanmış nesnenin işlevselliğini bilmelidir. Ancak, tüm nesneler toplanamaz. Toplanacak bir nesne için, dikkat etmeniz gereken toplama ile tasarlanmalıdır.

ATL, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'yi iki aşamada uygular:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md)veya `IUnknown` [CComPolyObject](../atl/reference/ccompolyobject-class.md) yöntemleri uygular.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) , başvuru sayısını ve `IUnknown`dış işaretçilerini yönetir.

ATL COM nesnenizin diğer yönleri diğer sınıflar tarafından işlenir:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) , nesnenin varsayılan sınıf fabrikası ve toplama modelini tanımlar.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) nesne üzerindeki herhangi bir çift arabirimin `IDispatch Interface` bölümünün varsayılan bir uygulamasını sağlar.

- [Iupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) , hata `ISupportErrorInfo` bilgilerinin çağrı zincirini doğru şekilde yayılmasını sağlayan arabirimi uygular.

## <a name="in-this-section"></a>Bu Bölümde

[CComObjectRootEx Uygulama](../atl/implementing-ccomobjectrootex.md)<br/>
Uygulamak `CComObjectRootEx`için örnek com eşleme girdilerini gösterir.

[CComObject, CComAggObject ve CComPolyObject Uygulama](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
`CComObject` **Declare_\*_toplanabilir** makroların ,`CComAggObject`, ve`CComPolyObject`kullanımını nasıl etkilediğini açıklar.

[IDispatch ve IErrorInfo Destekleme](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
`IDispatch` Ve`IErrorInfo` arabirimlerini desteklemek için kullanılacak atl uygulama sınıflarını listeler.

[IDispEventImpl Destekleme](../atl/supporting-idispeventimpl.md)<br/>
Sınıfınız için bir bağlantı noktası uygulamak için gereken adımları açıklar.

[Varsayılan Sınıf Üreteci ve Toplama Modelini Değiştirme](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Varsayılan sınıf fabrikası ve toplama modelini değiştirmek için kullanılacak makroları görüntüleyin.

[Toplanan Nesne oluşturma](../atl/creating-an-aggregated-object.md)<br/>
Toplu bir nesne oluşturmak için gereken adımları listeler.

## <a name="related-sections"></a>İlgili Bölümler

[ATL Projesi Oluşturma](../atl/reference/creating-an-atl-project.md)<br/>
ATL COM nesnesi oluşturma hakkında bilgi sağlar.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../atl/active-template-library-atl-concepts.md)
