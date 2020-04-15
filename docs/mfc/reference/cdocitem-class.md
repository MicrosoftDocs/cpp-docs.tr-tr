---
title: CdocItem Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 438bc2a03239946dbfca53d5f2989c731b682ab0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375617"
---
# <a name="cdocitem-class"></a>CdocItem Sınıfı

Belge nin verilerinin bileşenleri olan belge öğeleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDocItem::GetDocument](#getdocument)|Öğeyi içeren belgeyi döndürür.|
|[CdocItem::IsBlank](#isblank)|Öğenin herhangi bir bilgi içerip içermediğini belirler.|

## <a name="remarks"></a>Açıklamalar

`CDocItem`nesneler, hem istemci hem de sunucu belgelerinde OLE öğelerini temsil etmek için kullanılır.

Daha fazla bilgi için, makale [Kapsayıcılar bakın: Bir Kapsayıcı uygulama.](../../mfc/containers-implementing-a-container.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a>CDocItem::GetDocument

Öğeyi içeren belgeyi almak için bu işlevi arayın.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belgenin işaretçisi; NULL, öğe belgenin bir parçası değilse.

### <a name="remarks"></a>Açıklamalar

Bu işlev, [coleClientItem](../../mfc/reference/coleclientitem-class.md) ve [COleServerItem](../../mfc/reference/coleserveritem-class.md)türemiş sınıflarda geçersiz kılınır, bir işaretçi [coleDocument,](../../mfc/reference/coledocument-class.md) [cOleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)veya [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) nesnesine döndürülür.

## <a name="cdocitemisblank"></a><a name="isblank"></a>CdocItem::IsBlank

Varsayılan serileştirme gerçekleştiğinde çerçeve tarafından çağrılır.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bilgi içermisse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CDocItem` nesneler boş değildir. [COleClientItem](../../mfc/reference/coleclientitem-class.md) nesneleri bazen boştur, çünkü `CDocItem`doğrudan .'den türediler. Ancak, [COleServerItem](../../mfc/reference/coleserveritem-class.md) nesneleri her zaman boştur. Varsayılan olarak, x veya `COleClientItem` y boyutu olmayan nesneleri içeren OLE uygulamaları seri hale getirilmiştir. Bu, maddenin x veya y boyutu `IsBlank` olmadığında bir geçersiz kılmadan TRUE döndürülerek yapılır.

Serileştirme sırasında başka eylemler uygulamak istiyorsanız bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)
