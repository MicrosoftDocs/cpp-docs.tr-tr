---
title: CDocObjectServerItem Sınıfı
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
ms.openlocfilehash: 1f0f5cf93aab35a17f7174b2beee0d1398564a3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375534"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem Sınıfı

DocObject sunucuları için özel olarak OLE sunucu fiillerini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Bir `CDocObjectServerItem` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem::GetDocument](#getdocument)|Öğeyi içeren belgeiçin bir işaretçi alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CdocObjectServerItem::OndoVerb](#ondoverb)|Bir fiili yürütmek için çağrıldı.|
|[CdocObjectServerItem::OnHide](#onhide)|Çerçeve bir DocObject öğesini gizlemeye çalışırsa bir özel durum atar.|
|[CdocObjectServerItem::Onshow](#onshow)|DocObject öğesini yerinde etkin kılmak için çerçeve tarafından çağrılır. Öğe Bir DocObject değilse, [COleServerItem çağırır::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|

## <a name="remarks"></a>Açıklamalar

`CDocObjectServerItem`geçersiz üye işlevleri tanımlar: [OnHide](#onhide), [OnDoVerb](#ondoverb), ve [OnShow](#onshow).

Kullanmak `CDocObjectServerItem`için, türetilmiş `COleServerDoc`sınıfınızdaki [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) geçersiz kılmanın yeni `CDocObjectServerItem` bir nesne döndürür olduğundan emin olun. Öğenizdeki herhangi bir işlevselliği değiştirmeniz gerekiyorsa, kendi `CDocObjectServerItem`türetilmiş sınıfınızın yeni bir örneğini oluşturabilirsiniz.

DocObjects hakkında daha fazla bilgi için *MFC Başvurusu'nda* [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) ve [COleCmdUI'ye](../../mfc/reference/colecmdui-class.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[Coleserverıtem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdocob.h

## <a name="cdocobjectserveritemcdocobjectserveritem"></a><a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem

Bir `CDocObjectServerItem` nesne inşa eder.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*pServerDoc*<br/>
Yeni DocObject öğesini içerecek belgenin işaretçisi.

*bAutoDelete*<br/>
Bir bağlantı yayımlandığında nesnenin silinip silinemeyeceğini gösterir. `CDocObjectServerItem` Nesne belgenizin verilerinin ayrılmaz bir parçasıysa bağımsız değişkeni FALSE olarak ayarlayın. Nesne, belgenizin verilerinde çerçeve tarafından silinebilecek bir aralığı tanımlamak için kullanılan ikincil bir yapıysa, true olarak ayarlayın.

## <a name="cdocobjectserveritemgetdocument"></a><a name="getdocument"></a>CDocObjectServerItem::GetDocument

Öğeyi içeren belgeiçin bir işaretçi alır.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belgenin işaretçisi; Öğe belgenin bir parçası değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, [cdocobjectServerItem](#cdocobjectserveritem) oluşturucuya bağımsız değişken olarak geçtiğiniz sunucu belgesine erişim sağlar.

## <a name="cdocobjectserveritemondoverb"></a><a name="ondoverb"></a>CdocObjectServerItem::OndoVerb

Belirtilen fiili yürütmek için çerçeve tarafından çağrılır.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
Yürütmek için fiil belirtir. Olası değerler için Windows SDK'daki [IOleObject::DoVerb'e](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) bakın.

### <a name="remarks"></a>Açıklamalar

Öğe bir DocObject ise ve OLEIVERB_INPLACEACTIVATE veya OLEIVERB_SHOW belirtilmişse, varsayılan uygulama [OnShow](#onshow) üye işlevini çağırır. Öğe bir DocObject değilse veya farklı bir fiil belirtilirse, varsayılan uygulama [COleServerItem çağırır::OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb).

## <a name="cdocobjectserveritemonhide"></a><a name="onhide"></a>CdocObjectServerItem::OnHide

Öğeyi gizlemek için çerçeve tarafından çağrılır.

```
virtual void OnHide();
```

### <a name="remarks"></a>Açıklamalar

Öğe Bir DocObject ise varsayılan uygulama bir özel durum atar. Etkin bir DocObject öğesini gizleyemezsiniz, çünkü tüm görünümü alır. Kaybolması için DocObject öğesini devre dışı bırakmanız gerekir. Öğe Bir DocObject değilse, varsayılan uygulama [COleServerItem çağırır::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).

## <a name="cdocobjectserveritemonshow"></a><a name="onshow"></a>CdocObjectServerItem::Onshow

Sunucu uygulamasına DocObject öğesini yerinde etkin hale getirmetalimatı vermek için çerçeve tarafından çağrılır.

```
virtual void OnShow();
```

### <a name="remarks"></a>Açıklamalar

Öğe Bir DocObject değilse, varsayılan uygulama [COleServerItem çağırır::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Bir DocObject öğesini açarken özel işleme gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer Sınıfı](../../mfc/reference/cdocobjectserver-class.md)<br/>
[COleDocObjectItem Sınıfı](../../mfc/reference/coledocobjectitem-class.md)
