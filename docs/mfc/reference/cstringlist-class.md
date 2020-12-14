---
description: 'Daha fazla bilgi edinin: CStringList sınıfı'
title: CStringList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CStringList::CStringList
- AFXCOLL/CStringList::AddHead
- AFXCOLL/CStringList::AddTail
- AFXCOLL/CStringList::Find
- AFXCOLL/CStringList::FindIndex
- AFXCOLL/CStringList::GetAt
- AFXCOLL/CStringList::GetCount
- AFXCOLL/CStringList::GetHead
- AFXCOLL/CStringList::GetHeadPosition
- AFXCOLL/CStringList::GetNext
- AFXCOLL/CStringList::GetPrev
- AFXCOLL/CStringList::GetSize
- AFXCOLL/CStringList::GetTail
- AFXCOLL/CStringList::GetTailPosition
- AFXCOLL/CStringList::InsertAfter
- AFXCOLL/CStringList::InsertBefore
- AFXCOLL/CStringList::IsEmpty
- AFXCOLL/CStringList::RemoveAll
- AFXCOLL/CStringList::RemoveAt
- AFXCOLL/CStringList::RemoveHead
- AFXCOLL/CStringList::RemoveTail
- AFXCOLL/CStringList::SetAt
helpviewer_keywords:
- CStringList [MFC], CStringList
- CStringList [MFC], AddHead
- CStringList [MFC], AddTail
- CStringList [MFC], Find
- CStringList [MFC], FindIndex
- CStringList [MFC], GetAt
- CStringList [MFC], GetCount
- CStringList [MFC], GetHead
- CStringList [MFC], GetHeadPosition
- CStringList [MFC], GetNext
- CStringList [MFC], GetPrev
- CStringList [MFC], GetSize
- CStringList [MFC], GetTail
- CStringList [MFC], GetTailPosition
- CStringList [MFC], InsertAfter
- CStringList [MFC], InsertBefore
- CStringList [MFC], IsEmpty
- CStringList [MFC], RemoveAll
- CStringList [MFC], RemoveAt
- CStringList [MFC], RemoveHead
- CStringList [MFC], RemoveTail
- CStringList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
ms.openlocfilehash: c9043ef648f50e880f3b5946c1912deca3de6714
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345075"
---
# <a name="cstringlist-class"></a>CStringList sınıfı

Nesne listelerini destekler `CString` .

## <a name="syntax"></a>Syntax

```
class CStringList : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri, `CStringList` sınıf [CObList](../../mfc/reference/coblist-class.md)öğesinin üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CObList` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. `CObject`Dönüş değeri olarak bir işaretçi Gördüğünüz her yerde, bir `CString` (işaretçi değil) yerine koyun `CString` . `CObject`İşlev parametresi olarak bir işaretçi Gördüğünüz her yerde, yerine bir yazın `LPCTSTR` .

`CObject*& CObList::GetHead() const;`

Örneğin, öğesine çevirir

`CString& CStringList::GetHead() const;`

ve

`POSITION AddHead( CObject* <newElement> );`

çevirir

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStringList:: CStringList](../../mfc/reference/coblist-class.md#coblist)|Boş bir liste oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStringList:: AddHead](../../mfc/reference/coblist-class.md#addhead)|Listenin baş bir bir öğesini (veya başka bir listedeki tüm öğeleri) ekler (yeni bir baş oluşturur).|
|[CStringList:: AddTail](../../mfc/reference/coblist-class.md#addtail)|Bir öğeyi (veya başka bir listedeki tüm öğeleri) listenin sonuna ekler (yeni bir kuyruk oluşturur).|
|[CStringList:: Find](../../mfc/reference/coblist-class.md#find)|İşaretçi değeri tarafından belirtilen öğenin konumunu alır.|
|[CStringList:: FindIndex](../../mfc/reference/coblist-class.md#findindex)|Sıfır tabanlı bir dizin tarafından belirtilen öğenin konumunu alır.|
|[CStringList:: GetAt](../../mfc/reference/coblist-class.md#getat)|Belirtilen konumdaki öğeyi alır.|
|[CStringList:: GetCount](../../mfc/reference/coblist-class.md#getcount)|Bu listedeki öğe sayısını döndürür.|
|[CStringList:: GetHead](../../mfc/reference/coblist-class.md#gethead)|Listenin baş öğesini döndürür (boş olamaz).|
|[CStringList:: GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Listenin baş öğesinin konumunu döndürür.|
|[CStringList:: GetNext](../../mfc/reference/coblist-class.md#getnext)|Yineleme için bir sonraki öğeyi alır.|
|[CStringList:: Getöncekini](../../mfc/reference/coblist-class.md#getprev)|Yineleme için önceki öğeyi alır.|
|[CStringList:: GetSize](../../mfc/reference/coblist-class.md#getsize)|Bu listedeki öğe sayısını döndürür.|
|[CStringList:: GetTail](../../mfc/reference/coblist-class.md#gettail)|Listenin tail öğesini döndürür (boş olamaz).|
|[CStringList:: Getbir Position](../../mfc/reference/coblist-class.md#gettailposition)|Listenin tail öğesinin konumunu döndürür.|
|[CStringList:: InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Belirli bir konumdan sonra yeni bir öğe ekler.|
|[CStringList:: InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Belirli bir konumdan önce yeni bir öğe ekler.|
|[CStringList:: IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Boş liste koşulunu sınar (öğe yok).|
|[CStringList:: RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Bu listedeki tüm öğeleri kaldırır.|
|[CStringList:: RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Bu listeden, konuma göre belirtilen bir öğeyi kaldırır.|
|[CStringList:: RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Öğeyi listenin Başndan kaldırır.|
|[CStringList:: RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Öğeyi listenin tail öğesinden kaldırır.|
|[CStringList:: SetAt](../../mfc/reference/coblist-class.md#setat)|Belirtilen konumdaki öğeyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

Tüm karşılaştırmalar değere göre yapılır, bu da dizedeki karakterlerin dizelerin adresleri yerine karşılaştırılacağı anlamına gelir.

`CStringList` öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu ekler. Bir `CString` nesne listesi, aşırı yüklenmiş bir ekleme işleci veya üye işlevi ile bir arşive depolanıyorsa, `Serialize` her `CString` öğe sırayla serileştirilir.

Tek tek öğelerin bir dökümünden ihtiyacınız varsa `CString` , döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Kullanma hakkında daha fazla bilgi için `CStringList` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
