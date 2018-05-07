---
title: Etkin belgeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC]
- active documents [MFC], requirements
- view objects [MFC], requirements
- OLE [MFC], active documents
- views [MFC], active documents
- active documents [MFC], views
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7a391dda8f8ffee6cec3cebc9d03250336195db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="active-documents"></a>Etkin Belgeler
Etkin belgeler OLE bileşik belge teknolojisinin genişletir. Bu uzantılar, görünümler, böylece nesneleri kapsayıcılara işlev ve henüz kendi görüntüleme ve yazdırma işlevleri üzerinde denetimi korumak yöneten ek arabirimler biçiminde sağlanır. Bu işlem belgeleri yabancı çerçeveleri (örneğin, Microsoft Internet Explorer veya Microsoft Office Binder) hem de yerel çerçeveler (ürünün kendi görünüm bağlantı noktaları gibi) görüntülemek mümkün kılar.  
  
 Bu bölümde işlev açıklanmaktadır [etkin belgeler için gereksinimleri](#requirements_for_active_documents). Etkin belgeyi bir veri kümesi sahibi ve verileri nerede kaydedilmiş ve alınan depolama erişimi vardır. Bunu oluşturun ve verileri bir veya daha fazla görünümleri yönetin. Etkin belgeyi görünümleri aracılığıyla oluşturma yeteneğini iletişim kurar normal katıştırma OLE belgeleri yerinde etkinleştirme arabirimleri destekleyen ek olarak, `IOleDocument`. Bu arabirimi aracılığıyla kapsayıcı oluşturun (ve muhtemelen numaralandırmak) etkin belgeyi görüntüleyebileceği görünümleri sorabilirsiniz. Bu arabirim üzerinden, etkin belgeyi birden çok görünüm veya karmaşık dikdörtgenler destekleyip desteklemediğini gibi çeşitli bilgiler kendisi hakkında da sağlayabilir.  
  
 Aşağıdaki **IOleDocument** arabirimi. Unutmayın **IEnumOleDocumentViews** arabirimidir için standart bir OLE Numaralandırıcı **IOleDocumentView \***  türleri.  
  
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
  
 Her etkin belgeyi bu arabirime sahip bir görünüm çerçeve sağlayıcı olması gerekir. Belge bir kapsayıcıda katıştırılmış değil, etkin belge sunucusu görünüm çerçeve sağlamanız gerekir. Ancak, etkin belgeyi bir etkin belge kapsayıcısı katıştırıldığında, kapsayıcı görünüm çerçeve sağlar.  
  
 Etkin belge bir veya daha fazla tür oluşturabilirsiniz [görünümleri](#requirements_for_view_objects) verilerini (örneğin, normal, Anahat, sayfa düzeni ve benzeri). Görünümleri veri görülebilir filtreler gibi davranır. Belgeyi yalnızca bir görünüm türünü olsa bile, yine birden çok görünüm yeni pencere işlevleri destekleyen bir araç desteklemek istediğiniz (örneğin, **yeni pencere** üzerinde öğesi **penceresi** Office menüsü uygulamalar için).  
  
##  <a name="requirements_for_active_documents"></a> Etkin belgeler için gereksinimleri  
 Etkin belge kapsayıcısı içinde görüntülenebilir etkin bir belge gerekir:  
  
-   OLE'ın bileşik dosyaları uygulayarak kendi depolama mekanizması olarak kullanmak `IPersistStorage`.  
  
-   OLE dahil olmak üzere belgeler, temel katıştırma özelliklerini destekleyen **Dosyadan Oluştur**. Bu arabirimleri gerekir `IPersistFile`, `IOleObject`, ve `IDataObject`.  
  
-   Her biri yerinde etkinleştirme özelliğine sahip bir veya daha fazla görünümleri destekler. Diğer bir deyişle, görünümleri arabirimini desteklemelidir `IOleDocumentView` arabirimler yanı sıra `IOleInPlaceObject` ve `IOleInPlaceActiveObject` (kapsayıcının kullanarak **IOleInPlaceSite** ve **IOleInPlaceFrame** arabirimler).  
  
-   Destek standart etkin belgeyi arabirimler `IOleDocument`, `IOleCommandTarget`, ve `IPrint`.  
  
 Bilgi ne zaman ve nasıl kapsayıcı tarafı arabirimleri kullanılacağını bu gereksinimleri uygulanmaktadır.  
  
##  <a name="requirements_for_view_objects"></a> Görünüm nesneleri için gereksinimleri  
 Etkin belge verilerini bir veya daha fazla görünümler oluşturabilirsiniz. İşlevsel olarak, bu verileri görüntülemek için belirli bir yöntemin üzerine bağlantı noktaları gibi görünümlerdir. Etkin belgeyi yalnızca tek bir görünüm destekliyorsa, etkin belgeyi tek bir görünüm tek bir sınıf kullanarak uygulanabilir. **IOleDocument::CreateView** aynı nesnenin döndürür `IOleDocumentView` arabirim işaretçisi.  
  
 Etkin belge kapsayıcı içinde gösterilemeyecek kadar görünümü bileşen desteklemelidir **IOleInPlaceObject** ve **IOleInPlaceActiveObject** ek olarak `IOleDocumentView`:  
  
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
  
 Her görünüm görünüm çerçeve ve görünüm bağlantı noktası (HWND ve bu pencerede dikdörtgen bir) kapsayan bir ilişkili görünüm sitesi vardır. Site bu işlevselliği ancak standart kullanıma sunan **IOleInPlaceSite** arabirimi. Birden çok görünüm bağlantı noktasında tek bir HWND unutmayın.  
  
 Genellikle, her görünüm türü farklı yazdırılan gösterimi sahiptir. Bu nedenle görünümleri ve karşılık gelen siteleri görünümünü yazdırma arabirimleri varsa uygulamalıdır `IPrint` ve `IContinueCallback`sırasıyla. Görünüm çerçeve görünüm sağlayıcısı üzerinden ile anlaşmaları gerekir **IPrint** yazdırma başladığı, böylece üstbilgiler, altbilgiler, kenar boşluklarını ve ilgili öğeleri doğru yazdırılır. Görünüm Sağlayıcısı çerçevesi yazdırma ilgili olayların bildirir `IContinueCallback`. Bu arabirimleri kullanımı hakkında daha fazla bilgi için bkz: [programlı yazdırma](../mfc/programmatic-printing.md).  
  
 Etkin belgeyi yalnızca tek bir görünüm destekliyorsa, ardından etkin belgeyi ve bu tek bir görünüm tek somut bir sınıf kullanarak uygulanabilir olduğunu unutmayın. **IOleDocument::CreateView** yalnızca aynı nesnenin döndürür `IOleDocumentView` arabirim işaretçisi. Kısacası, yalnızca bir görünüm gerekli olduğunda, iki ayrı nesne örneğinin olması gerekli değildir.  
  
 Bir görünüm nesnesi, bir komut hedefi de olabilir. Uygulama tarafından `IOleCommandTarget` bir görünüm kapsayıcının kullanıcı arabiriminde kaynaklanan komutları alabilir (gibi **yeni**, **açık**, **Kaydet**,  **Yazdırma** üzerinde **dosya** menü; ve **kopya**, **Yapıştır**, **geri** üzerinde **Düzenle** menüsü). Daha fazla bilgi için bkz: [ileti işleme ve komut hedefleri](../mfc/message-handling-and-command-targets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin Belge Kapsaması](../mfc/active-document-containment.md)

