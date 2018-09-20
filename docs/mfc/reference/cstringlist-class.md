---
title: CStringList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3182a9f5a53c2f086800eb0eccb7d61e423e591
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439191"
---
# <a name="cstringlist-class"></a>CStringList sınıfı

Listelerini destekler `CString` nesneleri.

## <a name="syntax"></a>Sözdizimi

```
class CStringList : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CStringList` sınıfın üye işlevleri için benzer [CObList](../../mfc/reference/coblist-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObList` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir dönüş değeri olarak alternatif bir `CString` (değil bir `CString` işaretçisi). Gördüğünüz yerde bir `CObject` işaretçi işlevi parametre olarak, alternatif bir `LPCTSTR`.

`CObject*& CObList::GetHead() const;`

Örneğin, için çevirir

`CString& CStringList::GetHead() const;`

and

`POSITION AddHead( CObject* <newElement> );`

için çevirir

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Boş bir liste oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni head sağlar) listenin başındaki ekler.|
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni bir kuyruk sağlar) listesi kuyruğu için ekler.|
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|İşaretçi değeri tarafından belirtilen bir öğenin konumunu alır.|
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Sıfır tabanlı bir dizin tarafından belirtilen bir öğenin konumunu alır.|
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Öğesini, belirli bir konumda alır.|
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Bu listedeki öğelerin sayısını döndürür.|
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Head öğesi (boş olamaz) listesi döndürür.|
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Head öğesi listesinin konumunu döndürür.|
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Yineleme için sonraki öğeyi alır.|
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Yineleme için önceki öğeyi alır.|
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Bu listedeki öğelerin sayısını döndürür.|
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Kuyruk öğesini (boş olamaz) listesi döndürür.|
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Listenin tail öğenin konumunu döndürür.|
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Belirli bir pozisyon sonra yeni bir öğe ekler.|
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Belirli bir pozisyon önce yeni bir öğe ekler.|
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|(Öğe yok) boş liste koşulu sınar.|
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Bu listeden tüm öğeleri kaldırır.|
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Belirtilen konuma göre bu listeden bir öğeyi kaldırır.|
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Öğe listesinin başından kaldırır.|
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Öğe listesinin kuyruğunu kaldırır.|
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Öğe, belirli bir konumda ayarlar.|

## <a name="remarks"></a>Açıklamalar

Tüm karşılaştırmalar, yani dizedeki karakter dizeleri yerine adreslerini karşılaştırılır değeri tarafından gerçekleştirilir.

`CStringList` Serileştirme ve alt öğeleri dökme desteklemek için ımplement_serıal makrosu içerir. Bir listesini, `CString` nesneleri veya aşırı yüklenmiş bir ekleme operatörü ile birlikte bir arşivden depolandığı `Serialize` her üye işlev `CString` öğesi sırayla seri.

Tek bir dökümü gerekiyorsa `CString` öğeleri ayarlamanız gerekir döküm bağlam derinliğini 1 veya daha büyük.

Kullanma hakkında daha fazla bilgi için `CStringList`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek Topla](../../visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



