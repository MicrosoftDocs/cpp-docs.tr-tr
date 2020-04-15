---
title: ATL COM Nesnelerinin Temelleri
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 651413534ed44143e2a0fdaf00bdabd6e5d57010
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319553"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM Nesnelerinin Temelleri

Aşağıdaki resimde, bir ATL COM nesnesini tanımlamak için kullanılan sınıflar ve arabirimler arasındaki ilişki gösterilmiştir.

![ATL yapısı](../atl/media/vc307y1.gif "ATL yapısı")

> [!NOTE]
> Bu diyagram, `CComObject` oysa `CYourClass` `CComAggObject` türetilmiş `CComPolyObject` `CYourClass` ve bir üye değişken olarak içerir gösterir.

Bir ATL COM nesnesini tanımlamanın üç yolu vardır. Standart seçenek, `CComObject` `CYourClass`türetilen sınıfı kullanmaktır. İkinci `CComAggObject` seçenek, sınıfı kullanarak birleştirilmiş bir nesne oluşturmaktır. Üçüncü seçenek `CComPolyObject` sınıfı kullanmaktır. `CComPolyObject`bir melez olarak hareket eder: `CComObject` ilk nasıl `CComAggObject` oluşturulduğuna bağlı olarak, bir sınıf veya bir sınıf olarak işlev görebilir. `CComPolyObject` Sınıfın nasıl kullanılacağı hakkında daha fazla bilgi için [CComPolyObject Sınıfı'na](../atl/reference/ccompolyobject-class.md)bakın.

Standart ATL COM kullandığınızda, iki nesne kullanırsınız: bir dış nesne ve bir iç nesne. Dış istemciler dış nesnede tanımlanan sarıcı işlevleri aracılığıyla iç nesnenin işlevselliği erişin. Dış nesne türündedir. `CComObject`

Birleştirilmiş bir nesne kullandığınızda, dış nesne iç nesnenin işlevselliği için sarmalayıcılar sağlamaz. Bunun yerine, dış nesne doğrudan dış istemciler tarafından erişilen bir işaretçi sağlar. Bu senaryoda, dış nesne `CComAggObject`türündedir. İç nesne dış nesnenin bir üye değişkenidir `CYourClass`ve türündedir.

İstemci iç nesne ile etkileşim için dış nesne geçmesi gerekmez çünkü, toplanan nesneler genellikle daha verimlidir. Ayrıca, toplanan nesnenin arabiriminin doğrudan istemci tarafından kullanılabildiği göz önüne alındığında, dış nesnenin birleştirilmiş nesnenin işlevselliğini bilmesi gerekmez. Ancak, tüm nesneler toplanabilir. Bir nesnenin biraraya edilebilmesi için, toplanmış bir şekilde tasarlanması gerekir.

ATL, [IUnknown'u](/windows/win32/api/unknwn/nn-unknwn-iunknown) iki aşamada uygular:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), veya [CComPolyObject](../atl/reference/ccompolyobject-class.md) `IUnknown` yöntemleri uygular.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) veya [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) başvuru sayısı ve dış `IUnknown`işaretçiler yönetir.

ATL COM nesnenizin diğer yönleri diğer sınıflar tarafından işlenir:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) nesnenin varsayılan sınıf fabrika ve toplama modelini tanımlar.

- [iDispatchImpl](../atl/reference/idispatchimpl-class.md) nesne üzerinde herhangi `IDispatch Interface` bir çift arabirim bölümünün varsayılan bir uygulama sağlar.

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) hata `ISupportErrorInfo` bilgilerinin çağrı zincirini doğru bir şekilde yaymasını sağlayan arabirimi uygular.

## <a name="in-this-section"></a>Bu Bölümde

[CComObjectRootEx uygulama](../atl/implementing-ccomobjectrootex.md)<br/>
Uygulama için örnek COM `CComObjectRootEx`eşleme girişlerini göster.

[CComObject, CComAggObject ve CComPolyObject uygulama](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
**makroların _AGGREGATABLE\*DECLARE_** ve `CComObject` `CComAggObject` `CComPolyObject`.

[IDispatch ve IErrorInfo desteği](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
Arabirimleri `IDispatch` ve `IErrorInfo` arabirimleri desteklemek için kullanılacak ATL uygulama sınıflarını listeler.

[IDispEventImpl desteği](../atl/supporting-idispeventimpl.md)<br/>
Sınıfınız için bir bağlantı noktası uygulamak için adımları tartışır.

[Varsayılan Sınıf Fabrika ve Toplama Modelini Değiştirme](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Varsayılan sınıf fabrika sını ve toplama modelini değiştirmek için hangi makroların kullanılacağını gösterin.

[Birleştirilmiş Nesne Oluşturma](../atl/creating-an-aggregated-object.md)<br/>
Toplu nesne oluşturmak için adımları listeler.

## <a name="related-sections"></a>İlgili Bölümler

[ATL Projesi Oluşturma](../atl/reference/creating-an-atl-project.md)<br/>
Bir ATL COM nesnesi oluşturma hakkında bilgi sağlar.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon Kitaplığını kullanarak programlama ya da programlama hakkında kavramsal konulara bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
