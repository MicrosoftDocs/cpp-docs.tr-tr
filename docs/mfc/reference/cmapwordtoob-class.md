---
description: 'Daha fazla bilgi edinin: CMapWordToOb sınıfı'
title: CMapWordToOb sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapWordToOb
- AFXCOLL/CMapWordToOb
- AFXCOLL/CMapWordToOb::CMapWordToOb
- AFXCOLL/CMapWordToOb::GetCount
- AFXCOLL/CMapWordToOb::GetHashTableSize
- AFXCOLL/CMapWordToOb::GetNextAssoc
- AFXCOLL/CMapWordToOb::GetSize
- AFXCOLL/CMapWordToOb::GetStartPosition
- AFXCOLL/CMapWordToOb::HashKey
- AFXCOLL/CMapWordToOb::InitHashTable
- AFXCOLL/CMapWordToOb::IsEmpty
- AFXCOLL/CMapWordToOb::Lookup
- AFXCOLL/CMapWordToOb::LookupKey
- AFXCOLL/CMapWordToOb::RemoveAll
- AFXCOLL/CMapWordToOb::RemoveKey
- AFXCOLL/CMapWordToOb::SetAt
helpviewer_keywords:
- CMapWordToOb [MFC], CMapWordToOb
- CMapWordToOb [MFC], GetCount
- CMapWordToOb [MFC], GetHashTableSize
- CMapWordToOb [MFC], GetNextAssoc
- CMapWordToOb [MFC], GetSize
- CMapWordToOb [MFC], GetStartPosition
- CMapWordToOb [MFC], HashKey
- CMapWordToOb [MFC], InitHashTable
- CMapWordToOb [MFC], IsEmpty
- CMapWordToOb [MFC], Lookup
- CMapWordToOb [MFC], LookupKey
- CMapWordToOb [MFC], RemoveAll
- CMapWordToOb [MFC], RemoveKey
- CMapWordToOb [MFC], SetAt
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
ms.openlocfilehash: da21902c3789f1547055baffae5650fcb6b8c789
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336702"
---
# <a name="cmapwordtoob-class"></a>CMapWordToOb sınıfı

`CObject`16 bit sözcüklerle anahtarlanan işaretçilerin haritalarını destekler.

## <a name="syntax"></a>Syntax

```
class CMapWordToOb : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri `CMapWordToOb` [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CMapStringToOb` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CString` **`const`** işlev parametresi veya dönüş değeri olarak bir işaretçisi veya bir işaretçi Gördüğünüz her yerde **`char`** , sözcüğünü değiştirin.

`BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`

Örneğin, öğesine çevirir

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMapWordToOb:: CMapWordToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMapWordToOb:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapWordToOb:: GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapWordToOb:: GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CMapWordToOb:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapWordToOb:: GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapWordToOb:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapWordToOb:: InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tabloyu başlatır.|
|[CMapWordToOb:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Boş eşleme koşulunu sınar (öğe yok).|
|[CMapWordToOb:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void işaretçi tuşuna bağlı olarak void bir işaretçi arar. İşaret ettiği varlık değil işaretçi değeri, anahtar karşılaştırması için kullanılır.|
|[CMapWordToOb:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru döndürür.|
|[CMapWordToOb:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapWordToOb:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CMapWordToOb:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMapWordToOb:: işleci \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map içine bir öğe ekler — için işleç değiştirme `SetAt` .|

## <a name="remarks"></a>Açıklamalar

`CMapWordToOb` öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu ekler. Her bir öğe, aşırı yüklenmiş ekleme ( **<<** ) işleci veya member işlevi ile bir arşive depolanıyorsa, her öğe sırayla serileştirilir `Serialize` .

Tek sözcük öğelerinin bir dökümünden birine ihtiyacınız varsa `CObject` , döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CMapWordToOb` nesne silindiğinde veya öğeleri kaldırıldığında `CObject` işaretçiler kaldırılır. `CObject`İşaretçilerin başvurduğu nesneler yok edilmez.

Hakkında daha fazla bilgi için `CMapWordToOb` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapWordToOb`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
