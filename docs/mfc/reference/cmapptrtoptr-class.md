---
title: CMapPtrToPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
ms.openlocfilehash: a44b9524324065581583bad13018b2c4479fc9f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237757"
---
# <a name="cmapptrtoptr-class"></a>CMapPtrToPtr sınıfı

Void işaretçileriyle Anahtarlanan void işaretçilerin haritalarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMapPtrToPtr : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CMapPtrToPtr` sınıfın üye işlevleri için benzer [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CMapStringToOb` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir işlev parametre veya dönüş değeri olarak alternatif bir işaretçiye **void**. Gördüğünüz yerde bir `CString` veya **const** işaretçisine **char** işlevi parametre veya dönüş değeri bir işaretçiye yerine **void**.

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

Örneğin, için çevirir

`BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritada öğelerin sayısını döndürür.|
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Geçerli bir karma tablo içindeki öğelerin sayısını belirler.|
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için sonraki öğeyi alır.|
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritada öğelerin sayısını döndürür.|
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen bir anahtarı karma değerini hesaplar.|
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tablo başlatır.|
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|(Öğe yok) boş-map koşulu sınar.|
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void bir işaretçi void işaretçisine anahtara göre arar. İşaretçi değeri değil, işaret varlık anahtar karşılaştırma için kullanılır.|
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.|
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritayı bir öğe ekler; eşleşen bir anahtar bulunursa, var olan öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Haritayı bir öğe ekler; işleci alternatifi için `SetAt`.|

## <a name="remarks"></a>Açıklamalar

`CMapPtrToPtr` ımplement_dynamıc makrosu, çalışma zamanı tür erişimi ve dökme için desteği kapsayan bir `CDumpContext` nesne. Döküm (işaretçi değerler) bireysel harita öğelerinin gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

İşaretçi işaretçisi haritalar serileştirilemez.

Olduğunda bir `CMapPtrToPtr` nesnesi silindiğinde veya yalnızca işaretçiler öğelerine kaldırıldığında kaldırılır, bunlar başvuru varlıkları.

Daha fazla bilgi için `CMapPtrToPtr`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
