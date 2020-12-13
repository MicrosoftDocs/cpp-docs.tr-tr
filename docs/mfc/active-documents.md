---
description: 'Daha fazla bilgi edinin: etkin belgeler'
title: Etkin Belgeler
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
ms.openlocfilehash: cae0eda775670867d5e36b4f2b9ec895a5dc3eb7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150312"
---
# <a name="active-documents"></a>Etkin Belgeler

Etkin belgeler, OLE 'nin bileşik belge teknolojisini genişletir. Bu uzantılar, görünümleri yöneten Ek arabirimler biçiminde sağlanır. böylece nesneler kapsayıcılar içinde çalışabilir ve ancak görüntüleme ve yazdırma işlevleri üzerinde denetimi koruyabilir. Bu işlem, hem yabancı çerçevelerde (Microsoft Office Ciltçi veya Microsoft Internet Explorer gibi) hem de yerel çerçevelerde (ürünün kendi görünüm bağlantı noktaları gibi) belgeleri görüntülemeyi mümkün kılar.

Bu bölümde [etkin belgelerin işlevsel gereksinimleri](#requirements_for_active_documents)açıklanmaktadır. Etkin belge bir veri kümesine sahiptir ve verilerin kaydedilebileceği ve alınabileceği depolama alanına erişimi vardır. Verileri üzerinde bir veya daha fazla görünüm oluşturabilir ve yönetebilir. Etkin belge, OLE belgelerinin olağan ekleme ve yerinde etkinleştirme arabirimlerini desteklemeye ek olarak, aracılığıyla görünümler oluşturma yeteneğini de iletir `IOleDocument` . Bu arabirim aracılığıyla kapsayıcı, etkin belgenin görüntüleyeceği görünümleri oluşturmayı (ve muhtemelen numaralandırmanızı) isteyebilir. Bu arabirim aracılığıyla, etkin belge, birden fazla görünümü veya karmaşık dikdörtgeni destekleyip desteklememe gibi, kendisiyle ilgili çeşitli bilgiler de verebilir.

Arabirim aşağıda verilmiştir `IOleDocument` . `IEnumOleDocumentViews`Arabirimin türler için Standart BIR OLE numaralandırıcısı olduğunu unutmayın `IOleDocumentView*` .

```
interface IOleDocument : IUnknown
    {
    HRESULT CreateView(
        [in] IOleInPlaceSite *pIPSite,
        [in] IStream *pstm,
        [in] DWORD dwReserved,
        [out] IOleDocumentView **ppView);

    HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);

    HRESULT EnumViews(
        [out] IEnumOleDocumentViews **ppEnum,
        [out] IOleDocumentView **ppView);
    }
```

Her etkin belge, bu arabirime sahip bir görünüm Çerçevesi sağlayıcısına sahip olmalıdır. Belge bir kapsayıcı içinde katıştırılmadığından, etkin belge sunucusunun kendisi görünüm çerçevesini sağlaması gerekir. Ancak etkin belge etkin bir belge kapsayıcısına katıştırıldığında kapsayıcı, görünüm çerçevesini sağlar.

Etkin bir belge, verilerinin bir veya daha [fazla türünü (](#requirements_for_view_objects) Örneğin, normal, ana hat, sayfa düzeni vb.) oluşturabilir. Görünümler, verilerin görünebileceği filtreler gibi davranır. Belge yalnızca bir görünüm türüne sahip olsa bile, yeni pencere işlevselliğini destekleme (örneğin, Office uygulamalarındaki **pencere** menüsündeki **yeni pencere** öğesi) gibi birden fazla görünümü desteklemeye devam edebilirsiniz.

## <a name="requirements-for-active-documents"></a><a name="requirements_for_active_documents"></a> Etkin belgeler için gereksinimler

Etkin bir belge kapsayıcısında görüntülenebilen etkin bir belge şunları içermelidir:

- Uygulayarak, OLE 'nin bileşik dosyalarını depolama mekanizması olarak kullanın `IPersistStorage` .

- Dosyadan **Oluştur** da dahil olmak üzere OLE belgelerinin temel ekleme özelliklerini destekler. Bu, ve arabirimlerini gerektirir `IPersistFile` `IOleObject` `IDataObject` .

- Her biri yerinde etkinleştirme yeteneğine sahip olan bir veya daha fazla görünümü destekler. Diğer bir deyişle, görünümlerin arabirimi `IOleDocumentView` `IOleInPlaceObject` ve arabirimleri ve `IOleInPlaceActiveObject` (kapsayıcının `IOleInPlaceSite` ve `IOleInPlaceFrame` arabirimlerini kullanarak) desteklemesi gerekir.

- , Ve standart etkin belge arabirimlerini `IOleDocument` destekler `IOleCommandTarget` `IPrint` .

Kapsayıcı tarafı arabirimlerinin ne zaman ve nasıl kullanılacağı hakkında bilgi, bu gereksinimlerde nasıl ima edilir.

## <a name="requirements-for-view-objects"></a><a name="requirements_for_view_objects"></a> Görüntüleme nesneleri gereksinimleri

Etkin bir belge, verilerinin bir veya daha fazla görünümünü oluşturabilir. İşlevsellik, bu görünümler, verileri görüntülemek için belirli bir yönteme yönelik bağlantı noktaları gibidir. Etkin bir belge yalnızca tek bir görünümü destekliyorsa, etkin belge ve bu tek görünüm tek bir sınıf kullanılarak uygulanabilir. `IOleDocument::CreateView` aynı nesnenin `IOleDocumentView` arabirim işaretçisini döndürür.

Etkin bir belge kapsayıcısı içinde temsil edilebilmesi için bir görünüm bileşeninin şunları desteklemesi gerekir `IOleInPlaceObject` `IOleInPlaceActiveObject` `IOleDocumentView` :

```
interface IOleDocumentView : IUnknown
    {
    HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);
    HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);
    HRESULT GetDocument([out] IUnknown **ppunk);
    [input_sync] HRESULT SetRect([in] LPRECT prcView);
    HRESULT GetRect([in] LPRECT prcView);
    [input_sync] HRESULT SetRectComplex(
        [in] LPRECT prcView,
        [in] LPRECT prcHScroll,
        [in] LPRECT prcVScroll,
        [in] LPRECT prcSizeBox);
    HRESULT Show([in] BOOL fShow);
    HRESULT UIActivate([in] BOOL fUIActivate);
    HRESULT Open(void);
    HRESULT CloseView([in] DWORD dwReserved);
    HRESULT SaveViewState([in] IStream *pstm);
    HRESULT ApplyViewState([in] IStream *pstm);
    HRESULT Clone(
        [in] IOleInPlaceSite *pIPSiteNew,
        [out] IOleDocumentView **ppViewNew);
    }
```

Her görünüm, görünüm çerçevesini ve Görünüm bağlantı noktasını (HWND ve bu penceredeki bir dikdörtgen alanı) kapsülleyen ilişkili bir görünüm sitesine sahiptir. Site bu işlevselliği standart arabirim olarak kullanıma sunar `IOleInPlaceSite` . Tek bir HWND üzerinde birden fazla görünüm bağlantı noktası olması mümkün olduğunu unutmayın.

Genellikle, her bir görünüm türünün farklı bir yazdırılmış temsili vardır. Bu nedenle, görünümler ve ilgili görünüm siteleri sırasıyla yazdırma arabirimlerini uygulamalıdır `IPrint` `IContinueCallback` . Görünüm çerçevesi, yazdırma başladığında görünüm sağlayıcısıyla birlikte anlaşmalıdır `IPrint` , böylece üstbilgiler, altbilgiler, kenar boşlukları ve ilgili öğeler doğru şekilde yazdırılır. Görünüm sağlayıcısı, yazdırmayla ilgili olayların çerçevesini aracılığıyla bilgilendirir `IContinueCallback` . Bu arabirimlerin kullanımı hakkında daha fazla bilgi için bkz. [programlı yazdırma](programmatic-printing.md).

Etkin bir belge yalnızca tek bir görünümü destekliyorsa, etkin belge ve bu tek görünümün tek bir somut sınıf kullanılarak uygulankullanılamayacağını unutmayın. `IOleDocument::CreateView` yalnızca aynı nesnenin `IOleDocumentView` arabirim işaretçisini döndürür. Kısacası, yalnızca bir görünüm gerektiğinde iki ayrı nesne örneği olması gerekmez.

Bir görünüm nesnesi bir komut hedefi de olabilir. `IOleCommandTarget`Bir görünüm uygulayarak, kapsayıcının kullanıcı arabiriminden ( **Yeni**, **açma**, **farklı kaydet**, **Dosya** menüsünde **Yazdır** ) ve **kopyalama**, **Yapıştırma**, **geri alma** , **düzenleme** menüsünde yer alan komutları alabilir. Daha fazla bilgi için bkz. [Ileti işleme ve komut hedefleri](message-handling-and-command-targets.md).

## <a name="see-also"></a>Ayrıca bkz.

[Etkin belge kapsama](active-document-containment.md)
