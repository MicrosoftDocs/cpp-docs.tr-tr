---
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
ms.openlocfilehash: cbea3e032932477006820c5a71fbbf3e40123bdf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322081"
---
# <a name="active-documents"></a>Etkin Belgeler

Etkin belgeler OLE'nin bileşik belge teknolojisini genişletir. Bu uzantılar, nesnelerin kapsayıcılar içinde çalışabilmesi ve ancak görüntüleme ve yazdırma işlevleri üzerinde denetimini elinde tutabilmesi için görünümleri yöneten ek arabirimler şeklinde sağlanır. Bu işlem, belgeleri hem yabancı çerçevelerde (Microsoft Office Bağlayıcısı veya Microsoft Internet Gezgini gibi) hem de yerel çerçevelerde (ürünün kendi görünüm bağlantı noktaları gibi) görüntülemeyi mümkün kılar.

Bu [bölümde, etkin belgeler için](#requirements_for_active_documents)işlevsel gereksinimleri açıklanır. Etkin belge bir veri kümesine sahiptir ve verilerin kaydedilip alınabileceği depolama alanına erişimi vardır. Verileri üzerinde bir veya daha fazla görünüm oluşturabilir ve yönetebilir. Etkin belge, OLE belgelerinin olağan katıştırma ve yerinde etkinleştirme arabirimlerini desteklemenin `IOleDocument`yanı sıra, görüntüleme oluşturma yeteneğini de iletir. Bu arabirim aracılığıyla kapsayıcı, etkin belgenin görüntülebildiği görünümleri oluşturmasını (ve büyük olasılıkla sayısalatmasını) isteyebilir. Bu arabirim aracılığıyla, etkin belge, birden çok görünümü veya karmaşık dikdörtgenleri destekleyip desteklemediği gibi kendisi hakkında çeşitli bilgiler de sağlayabilir.

Aşağıdaki `IOleDocument` arayüzdür. `IEnumOleDocumentViews` Arabirimin türleri için `IOleDocumentView*` standart bir OLE eumerator olduğunu unutmayın.

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

Her etkin belge, bu arabirime sahip bir görünüm çerçeve sağlayıcısına sahip olmalıdır. Belge bir kapsayıcının içine katıştırılmış değilse, etkin belge sunucusunun kendisini görünüm çerçevesi sağlamalıdır. Ancak, etkin belge etkin bir belge kapsayıcıya katıştırıldığında, kapsayıcı görünüm çerçevesini sağlar.

Etkin bir belge, verilerinin (örneğin, normal, anahat, sayfa düzeni vb.) bir veya daha fazla [görünüm](#requirements_for_view_objects) türünü oluşturabilir. Görünümler, verilerin görülebileceği filtreler gibi davranır. Belgenin yalnızca bir görünüm türü olsa bile, yeni pencere işlevselliğini (örneğin, Office uygulamalarında **Pencere** menüsündeki **Yeni Pencere** öğesi) desteklemenin bir yolu olarak birden çok görünümü desteklemek isteyebilirsiniz.

## <a name="requirements-for-active-documents"></a><a name="requirements_for_active_documents"></a>Aktif Belgeler için Gereksinimler

Etkin bir belge kapsayıcısında görüntülenebilen etkin bir belgenin şunları yapması gerekir:

- Uygulayarak Depolama mekanizması olarak OLE'nin `IPersistStorage`Bileşik Dosyalarını kullanın.

- **Dosyadan Oluştur**gibi OLE Belgelerinin temel gömme özelliklerini destekleyin. Bu, arayüzleri `IPersistFile`gerektirir `IOleObject`, `IDataObject`, ve .

- Her biri yerinde etkinleştirme yeteneğine sahip bir veya daha fazla görünümü destekleyin. Diğer bir diğer adıyla, `IOleDocumentView` görünümler arabirimleri `IOleInPlaceObject` ve `IOleInPlaceActiveObject` (kapsayıcının `IOleInPlaceSite` ve `IOleInPlaceFrame` arabirimlerini kullanarak) arabirimi desteklemelidir.

- Standart etkin belge arabirimlerini `IOleDocument` `IOleCommandTarget` `IPrint`ve .

Kapsayıcı tarafındaki arabirimlerin ne zaman ve nasıl kullanılacağı bilgisi bu gereksinimlerde ima edilir.

## <a name="requirements-for-view-objects"></a><a name="requirements_for_view_objects"></a>Görünüm Nesneleri Için Gereksinimler

Etkin bir belge verilerinin bir veya daha fazla görünümü oluşturabilir. İşlevsel olarak, bu görünümler verileri görüntülemek için belirli bir yöntemüzerine bağlantı noktaları gibidir. Etkin bir belge yalnızca tek bir görünümü destekliyorsa, etkin belge ve bu tek görünüm tek bir sınıf kullanılarak uygulanabilir. `IOleDocument::CreateView`aynı nesnenin `IOleDocumentView` arabirim işaretçisini döndürür.

Etkin bir belge kapsayıcısı içinde temsil edilebilmek `IOleInPlaceActiveObject` için, `IOleDocumentView`bir görünüm bileşeninin desteklenmesi `IOleInPlaceObject` ve buna ek olarak:

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

Her görünümün, görünüm çerçevesini ve görünüm bağlantı noktasını (HWND ve bu penceredeki dikdörtgen bir alan) kapsayan ilişkili bir görünüm sitesi vardır. Site standart `IOleInPlaceSite` arabirim olsa bu işlevselliği ortaya çıkarır. Tek bir HWND'de birden fazla görünüm bağlantı noktası olmasının mümkün olduğunu unutmayın.

Genellikle, her görünüm türünün farklı bir yazdırılmış gösterimi vardır. Bu nedenle görünümler ve ilgili görünüm `IPrint` siteleri, `IContinueCallback`sırasıyla yazdırma arabirimlerini uygulamalıdır. Üstbilgiler, altbilgiler, kenar `IPrint` boşlukları ve ilgili öğelerin doğru şekilde yazdırılması için görünüm çerçevesi, yazdırma nın ne zaman başlayacağını görüntü sağlayıcısıyla görüşmelidir. Görünüm sağlayıcısı, yazdırmayla ilgili olayların çerçevesini `IContinueCallback`. Bu arabirimlerin kullanımı hakkında daha fazla bilgi için [Programlı Yazdırma](../mfc/programmatic-printing.md)bölümüne bakın.

Etkin bir belge yalnızca tek bir görünümü destekliyorsa, etkin belgenin ve tek görünümün tek bir somut sınıf kullanılarak uygulanabileceğini unutmayın. `IOleDocument::CreateView`yalnızca aynı nesnenin `IOleDocumentView` arabirim işaretçisini döndürür. Kısacası, yalnızca bir görünüm gerektiğinde iki ayrı nesne örneği olması gerekmez.

Görünüm nesnesi komut hedefi de olabilir. Bir görünüm `IOleCommandTarget` uygulayarak kapsayıcının kullanıcı arabiriminden kaynaklanan komutları alabilir **(Yeni**, **Aç**, **Kaydet**, **Dosya** menüsüne **Yazdır;** ve **Kopyala,** **Yapıştır,** **Düzenleme** menüsünde **geri al).** Daha fazla bilgi için [İleti İşleme ve Komut Hedefleri'ne](../mfc/message-handling-and-command-targets.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge İçerme](../mfc/active-document-containment.md)
