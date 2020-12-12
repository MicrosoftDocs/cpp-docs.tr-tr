---
description: 'Daha fazla bilgi edinin: CDocItem sınıfı'
title: CDocItem sınıfı
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
ms.openlocfilehash: 9e126d4351248165a3961739c13cc6ce7330c10c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185147"
---
# <a name="cdocitem-class"></a>CDocItem sınıfı

Belge öğeleri için temel sınıf, bir belge verilerinin bileşenleri.

## <a name="syntax"></a>Syntax

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDocItem:: GetDocument](#getdocument)|Öğeyi içeren belgeyi döndürür.|
|[CDocItem:: ISBLANK](#isblank)|Öğenin herhangi bir bilgi içerip içermediğini belirler.|

## <a name="remarks"></a>Açıklamalar

`CDocItem` nesneler, hem istemci hem de sunucu belgelerindeki OLE öğelerini temsil etmek için kullanılır.

Daha fazla bilgi için bkz. [kapsayıcılar: kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a> CDocItem:: GetDocument

Öğeyi içeren belgeyi almak için bu işlevi çağırın.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeyi içeren belgeye yönelik bir işaretçi; Öğe bir belgenin parçası değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Colet [belgesi](../../mfc/reference/coledocument-class.md), [Copalinkingdoc](../../mfc/reference/colelinkingdoc-class.md)ya da [copaserverdoc](../../mfc/reference/coleserverdoc-class.md) nesnesine bir Işaretçi döndüren türetilmiş sınıflarda [Cooclientidıtem](../../mfc/reference/coleclientitem-class.md) ve [copaserverıtem](../../mfc/reference/coleserveritem-class.md)içinde geçersiz kılınır.

## <a name="cdocitemisblank"></a><a name="isblank"></a> CDocItem:: ISBLANK

Varsayılan serileştirme gerçekleştiğinde Framework tarafından çağırılır.

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe hiçbir bilgi içermiyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CDocItem` nesneler boş değildir. Doğrudan türedikleri için [Colet Clienentitıtem](../../mfc/reference/coleclientitem-class.md) nesneleri bazen boş kalır `CDocItem` . Ancak [Coelserveritem](../../mfc/reference/coleserveritem-class.md) nesneleri her zaman boştur. Varsayılan olarak, `COleClientItem` x veya y uzantısı olmayan nesneler IÇEREN OLE uygulamaları serileştirilir. Bu, `IsBlank` öğenin x veya y uzantısı olmadığında bir geçersiz kılmanın true olarak döndürülerek yapılır.

Serileştirme sırasında başka eylemler uygulamak istiyorsanız bu işlevi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotadocument sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[Cotaserverıtem sınıfı](../../mfc/reference/coleserveritem-class.md)<br/>
[Colet Clienentidıtem sınıfı](../../mfc/reference/coleclientitem-class.md)
