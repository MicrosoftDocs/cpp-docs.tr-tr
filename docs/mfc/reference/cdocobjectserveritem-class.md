---
title: Cdocobjectserverıtem sınıfı
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
ms.openlocfilehash: cecbab366b64c85b39131a13233598abec83d5ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536532"
---
# <a name="cdocobjectserveritem-class"></a>Cdocobjectserverıtem sınıfı

DocObject sunucuları için özel OLE sunucu fiilleri uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Oluşturur bir `CDocObjectServerItem` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem::GetDocument](#getdocument)|Öğeyi içeren belge için bir işaretçi alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|DocObject öğesini gizlemek framework çalışırsa, bir özel durum oluşturur.|
|[CDocObjectServerItem::OnHide](#onhide)|DocObject öğesini gizlemek framework çalışırsa, bir özel durum oluşturur.|
|[CDocObjectServerItem::OnShow](#onshow)|DocObject öğesi yerleşik hale getirmek için framework tarafından çağırılır etkin. Öğe bir DocObject değil, çağıran [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|

## <a name="remarks"></a>Açıklamalar

`CDocObjectServerItem` geçersiz kılınabilir üye işlevleri tanımlar: [OnHide](#onhide), [OnDoVerb](#ondoverb), ve [OnShow](#onshow).

Kullanılacak `CDocObjectServerItem`, sağlanması, [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) içinde geçersiz kılmak, `COleServerDoc`-yeni bir türetilmiş sınıf döndürür `CDocObjectServerItem` nesne. Öğenizi herhangi bir işlevsellik değiştirmeniz gerekirse, yeni bir örneğini kendi oluşturabilirsiniz `CDocObjectServerItem`-türetilmiş sınıf.

DocObjects hakkında daha fazla bilgi için bkz: [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) ve [Colecmduı](../../mfc/reference/colecmdui-class.md) içinde *MFC başvurusu*.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocıtem](../../mfc/reference/cdocitem-class.md)

[Coleserverıtem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdocob.h

##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem

Oluşturur bir `CDocObjectServerItem` nesne.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*pServerDoc*<br/>
Yeni DocObject öğesini içeren belge işaretçisi.

*bAutoDelete*<br/>
Bağlantı yayımlandığında nesnesi silinebilir olup olmadığını gösterir. Bağımsız değişken FALSE olarak ayarlayın `CDocObjectServerItem` nesnedir, belgenin verilerini bir parçası. Framework tarafından silinebilir belgenizin veri aralığında tanımlamak için kullanılan bir ikincil yapısı nesneyse true ayarlayın.

##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument

Öğeyi içeren belge için bir işaretçi alır.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belge için bir işaretçi; Bir belge bir parçası değilse null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu bağımsız değişken olarak geçirilen sunucu belgeye erişimi verir [Cdocobjectserverıtem](#cdocobjectserveritem) Oluşturucusu.

##  <a name="onhide"></a>  CDocObjectServerItem::OnHide

Öğesini gizlemek için framework tarafından çağırılır.

```
virtual void OnHide();
```

### <a name="remarks"></a>Açıklamalar

Öğe bir DocObject ise varsayılan uygulaması bir özel durum oluşturur. Tam görünümü aldığından etkin DocObject öğeyi gizlenemez. Görünümden kaldırmak için DocObject öğesini devre dışı bırakmanız gerekir. Öğe bir DocObject değil, varsayılan uygulama çağrıları [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).

##  <a name="onshow"></a>  CDocObjectServerItem::OnShow

DocObject öğesi bağlantısı sağlamak için sunucu uygulamasının istemek için framework tarafından çağırılır etkin.

```
virtual void OnShow();
```

### <a name="remarks"></a>Açıklamalar

Öğe bir DocObject değil, varsayılan uygulama çağrıları [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Özel bir DocObject öğesini açılırken işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.

## <a name="see-also"></a>Ayrıca Bkz.

[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServer Sınıfı](../../mfc/reference/cdocobjectserver-class.md)<br/>
[COleDocObjectItem Sınıfı](../../mfc/reference/coledocobjectitem-class.md)
