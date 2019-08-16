---
title: CDocObjectServerItem sınıfı
ms.date: 03/27/2019
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnDoVerb
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnDoVerb
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: 4d44791415626f1a94500b9c3885581d67e8fe42
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506814"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem sınıfı

Özellikle DocObject sunucuları için OLE sunucu fiillerini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem:: CDocObjectServerItem](#cdocobjectserveritem)|Bir `CDocObjectServerItem` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem:: GetDocument](#getdocument)|Öğeyi içeren belgeye bir işaretçi alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem:: OnDoVerb](#ondoverb)|Bir fiil yürütmek için çağırılır.|
|[CDocObjectServerItem:: OnHide](#onhide)|Çerçeve bir DocObject öğesini gizlemeyi denediğinde bir özel durum oluşturur.|
|[CDocObjectServerItem:: OnShow](#onshow)|DocObject öğesini yerinde etkin hale getirmek için Framework tarafından çağırılır. Öğe bir DocObject değilse [Copaserverıtem:: OnShow](../../mfc/reference/coleserveritem-class.md#onshow)öğesini çağırır.|

## <a name="remarks"></a>Açıklamalar

`CDocObjectServerItem`geçersiz kılınabilir üye işlevlerini tanımlar: [OnHide](#onhide), [OnDoVerb](#ondoverb)ve [OnShow](#onshow).

Kullanmak `CDocObjectServerItem`için, türetilmiş sınıfınıza `COleServerDoc` [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) geçersiz kılmanın yeni `CDocObjectServerItem` bir nesne döndürdüğünden emin olmanız gerekir. Öğedeki işlevleri değiştirmeniz gerekiyorsa, kendi `CDocObjectServerItem`türetilmiş sınıfınızın yeni bir örneğini oluşturabilirsiniz.

DocObjects hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) ve [copacmduı](../../mfc/reference/colecmdui-class.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdocob. h

##  <a name="cdocobjectserveritem"></a>CDocObjectServerItem:: CDocObjectServerItem

Bir `CDocObjectServerItem` nesnesi oluşturur.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*pServerDoc*<br/>
Yeni DocObject öğesini içerecek belgeye yönelik bir işaretçi.

*bAutoDelete*<br/>
Bir bağlantı serbest bırakıldığında nesnenin silinip silinemeyeceğini gösterir. `CDocObjectServerItem` Nesne, belgenizin verilerinin integral bir parçasıysa bağımsız değişkeni false olarak ayarlayın. Nesne, çerçeve tarafından silinebilen belge verilerinde bir aralığı tanımlamak için kullanılan ikincil bir yapıdır, bunu TRUE olarak ayarlayın.

##  <a name="getdocument"></a>CDocObjectServerItem:: GetDocument

Öğeyi içeren belgeye bir işaretçi alır.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belgeye yönelik bir işaretçi; Öğe bir belgenin parçası değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, [CDocObjectServerItem](#cdocobjectserveritem) oluşturucusuna bağımsız değişken olarak geçirilmiş sunucu belgesine erişim sağlar.

##  <a name="ondoverb"></a>CDocObjectServerItem:: OnDoVerb

Belirtilen fiili yürütmek için Framework tarafından çağırılır.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
Yürütülecek fiili belirtir. Olası değerler için bkz. [IOleObject::D oVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, öğe bir DocObject ise ve OLEIVERB_INPLACEACTIVATE veya OLEIVERB_SHOW belirtilmişse [OnShow](#onshow) üye işlevini çağırır. Öğe bir DocObject değilse veya farklı bir fiil belirtilmişse, varsayılan uygulama [Copaserverıtem:: OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb)öğesini çağırır.

##  <a name="onhide"></a>CDocObjectServerItem:: OnHide

Öğeyi gizlemek için Framework tarafından çağırılır.

```
virtual void OnHide();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, öğe bir DocObject ise bir özel durum oluşturur. Tüm görünümü aldığı için etkin bir DocObject öğesini gizleyemezsiniz. Geçici hale getirmek için DocObject öğesini devre dışı bırakmanız gerekir. Öğe bir DocObject değilse, varsayılan uygulama [Cotaserverıtem:: OnHide](../../mfc/reference/coleserveritem-class.md#onhide)öğesini çağırır.

##  <a name="onshow"></a>CDocObjectServerItem:: OnShow

Sunucu uygulamasına DocObject öğesini yerinde etkin hale getirmek için Framework tarafından çağırılır.

```
virtual void OnShow();
```

### <a name="remarks"></a>Açıklamalar

Öğe bir DocObject değilse, varsayılan uygulama [Cotaserverıtem:: OnShow](../../mfc/reference/coleserveritem-class.md#onopen)öğesini çağırır. Bir DocObject öğesi açarken özel işlem gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer Sınıfı](../../mfc/reference/cdocobjectserver-class.md)<br/>
[COleDocObjectItem Sınıfı](../../mfc/reference/coledocobjectitem-class.md)
