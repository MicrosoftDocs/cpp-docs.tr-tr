---
title: 'Veri nesneleri ve veri kaynakları: Oluşturma ve yok etme'
ms.date: 11/04/2016
helpviewer_keywords:
- destroying data objects [MFC]
- object creation [MFC], data source objects
- data sources [MFC], and data objects
- data source objects [MFC], creating
- destruction [MFC], data sources
- data source objects [MFC], destroying
- data objects [MFC], creating
- data objects [MFC], destroying
- data sources [MFC], role
- data sources [MFC], destroying
- destruction [MFC], data objects
- data sources [MFC], creating
ms.assetid: ac216d54-3ca5-4ce7-850d-cd1f6a90d4f1
ms.openlocfilehash: 68ee5fbfec554df8865ca50c265ca2fa2f226a29
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775250"
---
# <a name="data-objects-and-data-sources-creation-and-destruction"></a>Veri nesneleri ve veri kaynakları: Oluşturma ve yok etme

Makalesinde açıklandığı gibi [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md), veri nesneleri ve veri kaynakları her iki tarafında bir veri aktarımı temsil eder. Bu makalede, oluşturmak ve bu nesneleri ve veri aktarımlarınız düzgün bir şekilde gerçekleştirmek için kaynakları yok etmek ne zaman dahil olmak üzere açıklanmaktadır:

- [Veri nesneleri oluşturma](#_core_creating_data_objects)

- [Veri nesnelerini yok etme](#_core_destroying_data_objects)

- [Veri kaynakları oluşturma](#_core_creating_data_sources)

- [Veri kaynakları yok etme](#_core_destroying_data_sources)

##  <a name="_core_creating_data_objects"></a> Veri nesneleri oluşturma

Veri nesneleri, hedef uygulama tarafından kullanılır — istemci veya sunucu. Hedef uygulama veri nesnesinde kaynak uygulama ve hedef uygulama arasında bir bağlantı sonudur. Hedef uygulama veri nesnesinde erişmek ve veri kaynağını verilerle etkileşim kurmak için kullanılır.

Bir veri nesnesi gerekmesi halinde iki yaygın durumlar vardır. Sürükle ve bırak kullanarak uygulamanızda veri bırakıldığında ilk durumudur. Düzen menüsü'nden yapıştırma veya Özel Yapıştır seçildiğinde ikinci durumdur.

Bir Sürükle ve bırak durumda veri nesnesi oluşturma gerekmez. Mevcut bir veri nesnesine bir işaretçi geçirilir, `OnDrop` işlevi. Bu veri nesnesi framework tarafından sürükle ve bırak işleminin bir parçası olarak oluşturulur ve sonra da edileceği. Yapıştırma başka bir yöntemle tamamlandığında bu her zaman böyle değildir. Daha fazla bilgi için [veri nesnelerini yok etme](#_core_destroying_data_objects).

Uygulama yapıştırın veya özel yapıştırma işlemi gerçekleştiriliyorsa oluşturmalısınız bir `COleDataObject` nesne ve çağrı kendi `AttachClipboard` üye işlevi. Veri nesnesi bu Panodaki veriler ile ilişkilendirir. Ardından, bu veri nesnesi Yapıştır işlevinizde kullanabilirsiniz.

##  <a name="_core_destroying_data_objects"></a> Veri nesnelerini yok etme

Açıklanan düzeni izlerseniz [veri nesneleri oluşturma](#_core_creating_data_objects), veri aktarımları önemsiz bir yönüyle olan veri nesnelerini yok etme. İşlev Yapıştır döndürdüğünde Yapıştır işlevinizde oluşturulduğu veri nesnesi MFC tarafından yok edilir.

Yapıştırma işlemlerine işlemenin başka bir yöntem izlerseniz, yapıştırma işlemi tamamlandıktan sonra veri nesnesi yok edildikten emin olun. Veri nesne yok edilene kadar herhangi bir uygulama verileri başarıyla panoya kopyalamak için mümkün olacaktır.

##  <a name="_core_creating_data_sources"></a> Veri kaynakları oluşturma

Veri kaynakları, istemci veya sunucu tarafı veri aktarımı olabilir veri aktarımı kaynağı tarafından kullanılır. Veri kaynağı kaynak uygulama içinde uygulama kaynak ve hedef uygulama arasında bir bağlantı sonudur. Hedef uygulama veri nesnesinde veri kaynağını verilerle etkileşim kurmak için kullanılır.

Veri kaynakları, bir uygulama verileri panoya kopyalamak gerektiğinde oluşturulur. Tipik bir senaryo şöyle çalışır:

1. Bazı verileri kullanıcı seçer.

1. Kullanıcının seçtiği **kopyalama** (veya **Kes**) öğesinden **Düzenle** menüsü veya bir Sürükle ve bırak işlemi başlar.

1. Program tasarımına bağlı olarak, uygulama ya da oluşturur bir `COleDataSource` veya nesneyi bir sınıftan türetilen `COleDataSource`.

1. Seçili verileri veri kaynağının işlevleri çağrılarak eklenir `COleDataSource::CacheData` veya `COleDataSource::DelayRenderData` grupları.

1. Uygulama çağrıları `SetClipboard` üye işlevi (veya `DoDragDrop` üye işlevi bir Sürükle ve bırak işlemi buysa) 3. adımda oluşturduğunuz nesneye ait.

1. Bu ise bir **Kes** işlemi veya `DoDragDrop` döndürür **DROPEFFECT_MOVE**, belge 1. adımda seçilen verileri silinir.

Bu senaryo, MFC OLE örnekleri tarafından uygulanan [OCLIENT](../overview/visual-cpp-samples.md) ve [HIERSVR](../overview/visual-cpp-samples.md). Her uygulama kaynağı bakın `CView`-türetilmiş sınıf için tüm `GetClipboardData` ve `OnGetClipboardData` işlevleri. Bu iki işlevler ötekisi `COleClientItem` veya `COleServerItem`-türetilmiş sınıf uygulamaları. Bu örnek programları nasıl uygulanacağını bu kavramları iyi bir örnek sağlar.

İçinde oluşturmak istediğiniz bir durum bir `COleDataSource` nesnesi, bir Sürükle ve bırak işlemi varsayılan davranışını değiştiriyorsanız gerçekleşir. Daha fazla bilgi için [sürükle ve bırak: Özelleştirme](../mfc/drag-and-drop-customizing.md) makalesi.

##  <a name="_core_destroying_data_sources"></a> Veri kaynakları yok etme

Veri kaynakları için şu anda sorumlu uygulama tarafından yok edilmelidir. Burada, teslim veri kaynağı için OLE durumlarda gibi çağırma [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop), çağırmanız gerekir `pDataSrc->InternalRelease`. Örneğin:

[!code-cpp[NVC_MFCListView#1](../atl/reference/codesnippet/cpp/data-objects-and-data-sources-creation-and-destruction_1.cpp)]

Veri kaynağınız için OLE devredildiği değil, siz gibi tipik bir C++ nesnesi ile yok etme için sorumlu olursunuz.

Daha fazla bilgi için [sürükle ve bırak](../mfc/drag-and-drop-ole.md), [Pano](../mfc/clipboard.md), ve [düzenleme veri nesneleri ve veri kaynakları](../mfc/data-objects-and-data-sources-manipulation.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Nesneleri ve Veri Kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md)<br/>
[COleDataObject sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource sınıfı](../mfc/reference/coledatasource-class.md)
