---
description: 'Daha fazla bilgi edinin: CDocObjectServer Class'
title: CDocObjectServer sınıfı
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
ms.openlocfilehash: 5a87363fef66a4819fc8efd504da96398cf3c89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184952"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer sınıfı

,,, Ve için normal bir sunucu oluşturmak için gereken ek OLE arabirimlerini uygular `COleDocument` :,, `IOleDocument` `IOleDocumentView` `IOleCommandTarget` ve `IPrint` .

## <a name="syntax"></a>Syntax

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Bir `CDocObjectServer` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServer:: ActivateDocObject](#activatedocobject)|Belge nesne sunucusunu etkinleştirir, ancak göstermez.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServer:: OnActivateView](#onactivateview)|DocObject görünümünü görüntüler.|
|[CDocObjectServer:: OnApplyViewState](#onapplyviewstate)|DocObject görünümünün durumunu geri yükler.|
|[CDocObjectServer:: OnSaveViewState](#onsaveviewstate)|DocObject görünümünün durumunu kaydeder.|

## <a name="remarks"></a>Açıklamalar

`CDocObjectServer` , ' dan türetilir `CCmdTarget` ve `COleServerDoc` arabirimleri kullanıma sunmak için ile yakından birlikte çalışarak.

Bir DocObject sunucu belgesi, DocObject öğelerine sunucu arabirimini temsil eden [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) nesneleri içerebilir.

DocObject sunucunuzu özelleştirmek için, kendi sınıfınızı ' dan türetirsiniz `CDocObjectServer` ve görünüm kurulum işlevlerini, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate)ve [OnSaveViewState](#onsaveviewstate)' i geçersiz kılın. Çerçeve çağrılarına yanıt olarak sınıfınızın yeni bir örneğini belirtmeniz gerekecektir.

DocObjects hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) ve [copacmduı](../../mfc/reference/colecmdui-class.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdocob. h

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a> CDocObjectServer:: ActivateDocObject

Belge nesne sunucusunu etkinleştirmek (ancak göstermek değil) için bu işlevi çağırın.

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>Açıklamalar

`ActivateDocObject` çağrılarının `IOleDocumentSite` `ActivateMe` yöntemi, ancak [CDocObjectServer:: OnActivateView](#onactivateview)çağrısında belirtilen görünümü ayarlama ve görüntüleme hakkında özel yönergeler beklediği için görünümü göstermez.

Birlikte, `ActivateDocObject` ve öğesini `OnActivateView` etkinleştirin ve DocObject görünümünü görüntüleyin. DocObject etkinleştirmesi diğer tür OLE yerinde etkinleştirmede farklılık gösterir. DocObject etkinleştirmesi, yerinde tarama kenarlıklarını ve nesne donatılarını (boyutlandırma tutamaçları gibi) görüntülemeyi atlar, nesne uzantısı işlevlerini yoksayar ve görünüm dikdörtgeni içinde kaydırma çubukları çizer (normal yerinde etkinleştirmeye benzer şekilde).

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a> CDocObjectServer::CDocObjectServer

Bir nesnesi oluşturur ve başlatır `CDocObjectServer` .

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>Parametreler

*pOwner*<br/>
DocObject sunucusu için istemci olan istemci sitesi belgesine yönelik bir işaretçi.

*Pdocsıte*<br/>
`IOleDocumentSite`Kapsayıcı tarafından uygulanan arabirime yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir DocObject etkin olduğunda, istemci sitesi OLE arabirimi (), `IOleDocumentSite` DocObject sunucusunun istemcisiyle (kapsayıcı) iletişim kurmasına izin verir. Bir DocObject sunucusu etkinleştirildiğinde, önce kapsayıcının arabirimini uygulayıp uygulamadığını denetler `IOleDocumentSite` . Bu durumda, kapsayıcının DocObjects 'i destekleyip desteklemediğini görmek için [Copaserverdoc:: GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) çağırılır. Varsayılan olarak, `GetDocObjectServer` null değerini döndürür. `COleServerDoc::GetDocObjectServer` `CDocObjectServer` `COleServerDoc` Kapsayıcının ve arabiriminin işaretçilerine bağımsız değişkenler olarak, yeni bir nesne veya türetilmiş bir nesne oluşturmak için geçersiz kılmanız gerekir `IOleDocumentSite` .

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a> CDocObjectServer:: OnActivateView

DocObject görünümünü görüntülemek için bu işlevi çağırın.

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir hata veya uyarı değeri döndürür. Varsayılan olarak, başarılı olursa NOERROR döndürür; Aksi takdirde, E_FAIL.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir yerinde çerçeve penceresi oluşturur, görünümün içinde kaydırma çubukları çizer, sunucu paylaşımlarının kapsayıcıyla birlikte menüler ayarlar, çerçeve denetimleri ekler, etkin nesneyi ayarlar, ardından son olarak yerinde çerçeve penceresini gösterir ve odağı ayarlar.

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a> CDocObjectServer:: OnApplyViewState

DocObject görünümünün durumunu geri yüklemek için bu işlevi geçersiz kılın.

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
`CArchive`Görünüm durumunun seri hale getirilecek bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, görünümü, örneği oluşturulduktan sonra ilk kez görüntülenirken çağrılır. `OnApplyViewState` bir görünümün kendisini, `CArchive` daha önce [OnSaveViewState](#onsaveviewstate)ile kaydedilen nesnedeki verilere göre yeniden başlatmasını söyler. `CArchive`Kapsayıcı, Görünüm durumu verilerini herhangi bir şekilde yorumlamaya çalışmadığından nesnenin verileri doğrulaması gerekir.

`OnSaveViewState`Görünümü, görünümlerinizin durumuna özgü kalıcı bilgileri depolamak için kullanabilirsiniz. `OnSaveViewState`Bilgileri depolamak için geçersiz kıldıysanız, `OnApplyViewState` Bu bilgileri okumak ve yeni etkinleştirildiğinde görünümse uygulamak için geçersiz kılmak isteyeceksiniz.

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a> CDocObjectServer:: OnSaveViewState

DocObject görünüminizdeki ek durum bilgilerini kaydetmek için bu işlevi geçersiz kılın.

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
`CArchive`Görünüm durumunun serileştirildiği bir nesne.

### <a name="remarks"></a>Açıklamalar

Durumlarınız görünüm türü, yakınlaştırma faktörü, ekleme ve seçim noktası gibi özellikleri içerebilir. Kapsayıcı genellikle bu işlevi, görünümü devre dışı bırakmadan önce çağırır. Kaydedilen durum daha sonra [OnApplyViewState](#onapplyviewstate)aracılığıyla geri yüklenebilir.

`OnSaveViewState`Görünümü, görünümlerinizin durumuna özgü kalıcı bilgileri depolamak için kullanabilirsiniz. `OnSaveViewState`Bilgileri depolamak için geçersiz kıldıysanız, `OnApplyViewState` Bu bilgileri okumak ve yeni etkinleştirildiğinde görünümse uygulamak için geçersiz kılmak isteyeceksiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServerItem sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
