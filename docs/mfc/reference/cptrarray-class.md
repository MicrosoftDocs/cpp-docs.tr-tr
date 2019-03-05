---
title: CPtrArray Class
ms.date: 11/04/2016
f1_keywords:
- CPtrArray
- AFXCOLL/CPtrArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: c23b87a3-bf84-49d6-a66b-61e999d0938a
ms.openlocfilehash: 59ecf01b81c4150e2bdae3b6d2862c1b3e91152b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281726"
---
# <a name="cptrarray-class"></a>CPtrArray Class

Void işaretçileri dizilerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CPtrArray : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CPtrArray` sınıfın üye işlevleri için benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObArray` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir işlev parametre veya dönüş değeri olarak alternatif bir işaretçiye **void**.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

Örneğin, için çevirir

`void* CPtrArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; dizi gerekirse büyür.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Diziyi başka diziye ekler; dizi gerekirse büyür.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizide öğelere erişim sağlar. Olabilir `NULL`.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizinini döndürür.|
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizi boş olup olmadığını belirler.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizisinden tüm öğeleri kaldırır.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki öğeyi kaldırır.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizinin içinde yer alması için öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::operator \[ \]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CPtrArray` ımplement_dynamıc makrosu, çalışma zamanı tür erişimi ve dökme için desteği kapsayan bir `CDumpContext` nesne. Tek tek işaretçisi, dizi öğelerinin bir döküm gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

> [!NOTE]
>  Bir dizi kullanmadan önce kullanmayı `SetSize` boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.

İşaretçi dizileri nelze serializovat.

Yalnızca işaretçiler, bir işaretçi dizisi silindiğinde veya öğeleri kaldırıldığında kaldırılır, bunlar başvuru varlıkları.

Kullanma hakkında daha fazla bilgi için `CPtrArray`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CPtrArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
