---
title: CDocObjectServer Sınıfı
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
ms.openlocfilehash: f415df35b13e50eee092f87eca0627e5cf143720
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753287"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer Sınıfı

Normal `COleDocument` bir sunucuyu tam bir DocObject sunucusuna dönüştürmek için `IOleDocument`gereken `IOleDocumentView` `IOleCommandTarget`ek `IPrint`OLE arabirimlerini uygular: , , ve .

## <a name="syntax"></a>Sözdizimi

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Bir `CDocObjectServer` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Belge nesnesi sunucusuetkinleştirir, ancak göstermez.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CdocObjectServer::OnactivateView](#onactivateview)|DocObject görünümünü görüntüler.|
|[CdocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject görünümünün durumunu geri yükler.|
|[CdocObjectServer::OnSaveViewState](#onsaveviewstate)|DocObject görünümünün durumunu kaydeder.|

## <a name="remarks"></a>Açıklamalar

`CDocObjectServer`türetilir `CCmdTarget` ve arabirimleri `COleServerDoc` ortaya çıkarmak için yakın çalışır.

DocObject sunucu belgesi, Sunucu arabirimini DocObject öğelerine temsil eden [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) nesneleri içerebilir.

DocObject sunucunuzu özelleştirmek için kendi sınıfınızı türetin ve görünüm kurulum işlevlerini, `CDocObjectServer` [OnActivateView,](#onactivateview) [OnApplyViewState](#onapplyviewstate)ve [OnSaveViewState'i](#onsaveviewstate)geçersiz kılın. Çerçeve çağrılarına yanıt olarak sınıfınızın yeni bir örneğini sağlamanız gerekir.

DocObjects hakkında daha fazla bilgi için *MFC Başvurusu'nda* [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) ve [COleCmdUI'ye](../../mfc/reference/colecmdui-class.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdocob.h

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject

Belge nesnesi sunucusunu etkinleştirmek (ancak göstermemek) için bu işlevi arayın.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Açıklamalar

`ActivateDocObject`'s `IOleDocumentSite` `ActivateMe` yöntemini çağırır, ancak CDocObjectServer'a yapılan çağrıda verilen görünümün nasıl ayarlanıp görüntülenenebildiği hakkında belirli yönergeleri beklediği için görünümü [göstermez::OnActivateView](#onactivateview).

Birlikte `ActivateDocObject` ve `OnActivateView` etkinleştirin ve DocObject görünümünü görüntüleyin. DocObject etkinleştirme, diğer OLE yerinde etkinleştirme türlerinden farklıdır. DocObject etkinleştirme, yerinde ambar kenarlıkları ve nesne süslemelerini (boyutlandırma tutamaçları gibi) görüntüleyen atlar, nesne kapsamı işlevlerini yok sayar ve görünüm dikdörtgeninin içinde kaydırma çubukları çizer, bu dikdörtgenin dışına çizim yapmak yerine (normal yerinde etkinleştirmede olduğu gibi).

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer

Bir `CDocObjectServer` nesne yi inşa eder ve başharfe ait hale raz.

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>Parametreler

*pSahibi*<br/>
DocObject sunucusunun istemcisi olan istemci site belgesine işaretçi.

*pDocSite*<br/>
Kapsayıcı tarafından `IOleDocumentSite` uygulanan arabirime işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir DocObject etkin olduğunda, istemci sitesi `IOleDocumentSite`OLE arabirimi ( ) DocObject sunucusunun istemcisiyle (kapsayıcı) iletişim kurmasına olanak tanır. Bir DocObject sunucusu etkinleştirildiğinde, önce kapsayıcının arabirimi uyguladığını `IOleDocumentSite` denetler. Eğer öyleyse, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) kapsayıcı DocObjects destekler olmadığını görmek için denir. Varsayılan olarak, `GetDocObjectServer` NULL döndürür. Yeni `COleServerDoc::GetDocObjectServer` `CDocObjectServer` bir nesne veya kendi türemiş bir nesne oluşturmak için `COleServerDoc` geçersiz kılmanız gerekir, kapsayıcı işaretçileri ve oluşturucu için bağımsız değişkenolarak arabirimi ile. `IOleDocumentSite`

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a>CdocObjectServer::OnactivateView

DocObject görünümünü görüntülemek için bu işlevi arayın.

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hata veya uyarı değeri verir. Varsayılan olarak, başarılı olursa NOERROR döndürür; aksi takdirde, E_FAIL.

### <a name="remarks"></a>Açıklamalar

Bu işlev yerinde bir çerçeve penceresi oluşturur, görünüm içinde kaydırma çubukları çizer, sunucunun kapsayıcısıyla paylaştığı menüleri ayarlar, çerçeve denetimleri ekler, etkin nesneyi ayarlar, sonra nihayet yerinde çerçeve penceresini gösterir ve odağı ayarlar.

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a>CdocObjectServer::OnApplyViewState

DocObject görünümünün durumunu geri yüklemek için bu işlevi geçersiz kılın.

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Görünüm `CArchive` durumunu seri hale getirmek için bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev, görünüm anlık olarak görüntülendikten sonra ilk kez görüntülendiğinde çağrılır. `OnApplyViewState`daha önce `CArchive` [OnSaveViewState](#onsaveviewstate)ile kaydedilen nesnedeki verilere göre kendisini yeniden başlatması için bir görünüm bildirir. Kapsayıcı görünüm durumu verilerini `CArchive` herhangi bir şekilde yorumlamaya çalışmadığından, görünüm nesnedeki verileri doğrulamalıdır.

Görünümünüzün `OnSaveViewState` durumuna özgü kalıcı bilgileri depolamak için kullanabilirsiniz. Bilgileri depolamak `OnSaveViewState` için geçersiz kılarsanız, bu `OnApplyViewState` bilgileri okumak ve yeni etkinleştirildiğinde görünümünüze uygulamak için geçersiz kılmak isteyebilirsiniz.

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a>CdocObjectServer::OnSaveViewState

DocObject görünümünüz hakkında ek durum bilgilerini kaydetmek için bu işlevi geçersiz kılın.

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Görünüm `CArchive` durumunun seri hale getirildiği bir nesne.

### <a name="remarks"></a>Açıklamalar

Durumunuz görünüm türü, yakınlaştırma faktörü, ekleme ve seçim noktası gibi özellikleri içerebilir. Kapsayıcı genellikle görünümü devre dışı atmadan önce bu işlevi çağırır. Kaydedilen durum daha sonra [OnApplyViewState](#onapplyviewstate)aracılığıyla geri yüklenebilir.

Görünümünüzün `OnSaveViewState` durumuna özgü kalıcı bilgileri depolamak için kullanabilirsiniz. Bilgileri depolamak `OnSaveViewState` için geçersiz kılarsanız, bu `OnApplyViewState` bilgileri okumak ve yeni etkinleştirildiğinde görünümünüze uygulamak için geçersiz kılmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServerItem Sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
