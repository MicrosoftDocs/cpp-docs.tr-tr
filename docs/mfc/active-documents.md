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
ms.openlocfilehash: 519dd51ab9b46adf862999104e97c6e478ccd86b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269246"
---
# <a name="active-documents"></a>Etkin Belgeler

Etkin belgeler OLE bileşik belge teknolojisini genişletir. Bu uzantılar, görünümler, böylece nesneleri kapsayıcılara işlev ve henüz, görüntü ve yazdırma işlevler üzerinde denetim korumak yöneten ek arabirimleri biçiminde sağlanır. Bu işlem, yabancı çerçeveleri (örneğin, Microsoft Office Binder ya da Microsoft Internet Explorer) hem de yerel çerçeveler (örneğin, ürünün kendi görünüm bağlantı noktaları) belgeleri görüntülemeyi mümkün kılar.

Bu bölümde işlevsel açıklanmaktadır [etkin belgeler için gereksinimleri](#requirements_for_active_documents). Etkin belgeyi bir veri kümesi sahibi ve verileri nerede kaydedildi ve alınan depolama erişebilir. Bu oluşturabilir ve kendi veri çubuğunda bir veya daha fazla görünüm yönetebilirsiniz. Her zamanki ekleme ve yerinde etkinleştirme arabirimleri OLE belgeleri hizmetinin yanı sıra, etkin belgeyi üzerinden görünümlerini oluşturma yeteneğini iletişim kuran `IOleDocument`. Bu arabirimi aracılığıyla, kapsayıcı oluşturma (ve muhtemelen Listeleme) etkin belgeyi görüntüleyen görüşnümleri isteyebilirsiniz. Bu arabirimi aracılığıyla, etkin belgeyi birden çok görünüm veya karmaşık dikdörtgenler destekleyip desteklemediğini gibi kendisi hakkında diğer bilgileri de sağlayabilirsiniz.

Aşağıdaki `IOleDocument` arabirimi. Unutmayın `IEnumOleDocumentViews` arabirimidir için standart bir OLE Numaralandırıcı `IOleDocumentView*` türleri.

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

Her etkin belge görünümü çerçeve sağlayıcısı bu arabirime sahip olmalıdır. Etkin belge sunucusu, belgeyi bir kapsayıcı içinde gömülü değilse görünümü çerçeve sağlamanız gerekir. Ancak, etkin belgeyi bir etkin belgeyi kapsayıcısında katıştırıldığında, kapsayıcı görünümü çerçeve sağlar.

Etkin belge bir veya daha fazla türde oluşturabilirsiniz [görünümleri](#requirements_for_view_objects) verilerini (örneğin, normal, Anahat, sayfa düzenini ve benzeri). Görünümleri veri görülebilir filtreler gibi davranır. Belge görünümü yalnızca bir tür olsa bile, yine de birden çok görünüm yeni pencere işlevleri destekleyen bir araç desteklemek istediğiniz (örneğin, **yeni pencere** üzerinde öğesi **penceresi** Office menüsü uygulamalar için).

##  <a name="requirements_for_active_documents"></a> Etkin belgeler için gereksinimleri

Bir etkin belge kapsayıcı içinde görüntülenen bir etkin belgeyi gerekir:

- Uygulayarak kendi depolama mekanizması olarak OLE'nin bileşik dosyalarını kullan `IPersistStorage`.

- OLE dahil olmak üzere belgeler, temel ekleme özelliklerinin desteklenmesi **Dosyadan Oluştur**. Bu arabirimler BIOS'ta `IPersistFile`, `IOleObject`, ve `IDataObject`.

- Her biri yerinde etkinleştirme özelliğine sahip olan bir veya daha fazla görünümleri destekler. Diğer bir deyişle, görünümleri arabirimini desteklemelidir `IOleDocumentView` arabirimlerin yanı sıra `IOleInPlaceObject` ve `IOleInPlaceActiveObject` (kapsayıcının kullanarak `IOleInPlaceSite` ve `IOleInPlaceFrame` arabirimleri).

- Destek standart etkin belgeyi arabirimler `IOleDocument`, `IOleCommandTarget`, ve `IPrint`.

Bilgi ne zaman ve nasıl kapsayıcı tarafı arabirimleri kullanır. Bu gereksinimleri belirtilir.

##  <a name="requirements_for_view_objects"></a> Görünüm nesneleri için gereksinimleri

Etkin belge verilerini bir veya daha fazla görünüm oluşturabilirsiniz. İşlevsel olarak, bu verileri görüntülemek için belirli bir yöntemin üzerine bağlantı noktaları gibi görünümleridir. Etkin belge yalnızca tek bir görünümde destekliyorsa, etkin belgeyi tek bir görünüm kullanarak tek bir sınıf uygulanabilir. `IOleDocument::CreateView` aynı nesne döndürür `IOleDocumentView` arabirim işaretçisi.

Bileşeni görüntüle bir etkin belge kapsayıcısı içinden gösterilemeyecek kadar desteklemelidir `IOleInPlaceObject` ve `IOleInPlaceActiveObject` ek olarak `IOleDocumentView`:

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

Her görünüm, görünüm çerçeve ve görünüm bağlantı noktası (HWND ve bu pencerede bir dikdörtgen alan) kapsayan bir ilişkili görünüm site sahiptir. Site bu işlevsellik ancak standart sunduğu `IOleInPlaceSite` arabirimi. Tek bir HWND üzerinde birden fazla görünümü bağlantı sağlamak Not.

Genellikle, her görünüm türü farklı bir yazdırılan gösterimi vardır. Bu nedenle Görünüm ve karşılık gelen görünüm siteleri yazdırma arabirimleri varsa uygulamalıdır `IPrint` ve `IContinueCallback`sırasıyla. Görünüm çerçeve görünüm sağlayıcısı aracılığıyla ile anlaşma gerekir `IPrint` yazdırma başladığı, böylece üstbilgiler, altbilgiler, kenar boşlukları ve ilgili öğeleri doğru yazdırılır. Görünüm sağlayıcısı yazdırma ilgili olayların çerçeve bildirir `IContinueCallback`. Bu arabirimler kullanımı hakkında daha fazla bilgi için bkz. [programlı yazdırma](../mfc/programmatic-printing.md).

Etkin belge yalnızca tek bir görünümde destekliyorsa, sonra etkin belgeyi ve tek bir görünüm kullanarak tek bir somut sınıf uygulanabilir olduğunu unutmayın. `IOleDocument::CreateView` yalnızca aynı nesne döndürür `IOleDocumentView` arabirim işaretçisi. Kısacası, yalnızca bir görünüm gerekli olduğunda, iki ayrı nesne örneğinin olması gerekli değildir.

Bir komut hedefi bir görünüm nesnesi yapılabilir. Uygulayarak `IOleCommandTarget` kapsayıcının kullanıcı arabiriminde kaynaklanan komutları bir görünümünü alabilir (gibi **yeni**, **açık**, **Kaydet**,  **Yazdırma** üzerinde **dosya** menüsü ve **kopyalama**, **Yapıştır**, **geri** üzerinde **Düzenle** menü). Daha fazla bilgi için [ileti işleme ve komut hedefleri](../mfc/message-handling-and-command-targets.md).

## <a name="see-also"></a>Ayrıca bkz.

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)
