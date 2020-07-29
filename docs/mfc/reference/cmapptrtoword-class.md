---
title: CMapPtrToWord sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToWord
- AFXCOLL/CMapPtrToWord
- AFXCOLL/CMapPtrToWord::CMapPtrToWord
- AFXCOLL/CMapPtrToWord::GetCount
- AFXCOLL/CMapPtrToWord::GetHashTableSize
- AFXCOLL/CMapPtrToWord::GetNextAssoc
- AFXCOLL/CMapPtrToWord::GetSize
- AFXCOLL/CMapPtrToWord::GetStartPosition
- AFXCOLL/CMapPtrToWord::HashKey
- AFXCOLL/CMapPtrToWord::InitHashTable
- AFXCOLL/CMapPtrToWord::IsEmpty
- AFXCOLL/CMapPtrToWord::Lookup
- AFXCOLL/CMapPtrToWord::LookupKey
- AFXCOLL/CMapPtrToWord::RemoveAll
- AFXCOLL/CMapPtrToWord::RemoveKey
- AFXCOLL/CMapPtrToWord::SetAt
helpviewer_keywords:
- CMapPtrToWord [MFC], CMapPtrToWord
- CMapPtrToWord [MFC], GetCount
- CMapPtrToWord [MFC], GetHashTableSize
- CMapPtrToWord [MFC], GetNextAssoc
- CMapPtrToWord [MFC], GetSize
- CMapPtrToWord [MFC], GetStartPosition
- CMapPtrToWord [MFC], HashKey
- CMapPtrToWord [MFC], InitHashTable
- CMapPtrToWord [MFC], IsEmpty
- CMapPtrToWord [MFC], Lookup
- CMapPtrToWord [MFC], LookupKey
- CMapPtrToWord [MFC], RemoveAll
- CMapPtrToWord [MFC], RemoveKey
- CMapPtrToWord [MFC], SetAt
ms.assetid: 4631c6b6-d49f-49d9-adc0-1e0491e32d7b
ms.openlocfilehash: 254659a9f00ff7c0c27174cfbea4c131993150f3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223037"
---
# <a name="cmapptrtoword-class"></a>CMapPtrToWord sınıfı

Void işaretçilerle anahtarlı 16 bit sözcüklerin haritalarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMapPtrToWord : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri `CMapPtrToWord` [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CMapStringToOb` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işlev parametresi veya dönüş değeri olarak bir işaretçi Gördüğünüz her yerde, sözcüğünü değiştirin. `CString` **`const`** İşlev parametresi veya dönüş değeri olarak bir işaretçisi veya bir işaretçi Gördüğünüz her yerde **`char`** , bir işaretçisi yerine **`void`** .

`BOOL CMapPtrToWord::Lookup( const void* <key>, WORD& <rValue> ) const;`

Örneğin, öğesine çevirir

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMapPtrToWord:: CMapPtrToWord](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMapPtrToWord:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapPtrToWord:: GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapPtrToWord:: GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CMapPtrToWord:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapPtrToWord:: GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapPtrToWord:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapPtrToWord:: InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tabloyu başlatır.|
|[CMapPtrToWord:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Boş eşleme koşulunu sınar (öğe yok).|
|[CMapPtrToWord:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void işaretçi tuşuna bağlı olarak void bir işaretçi arar. İşaret ettiği varlık değil işaretçi değeri, anahtar karşılaştırması için kullanılır.|
|[CMapPtrToWord:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru döndürür.|
|[CMapPtrToWord:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapPtrToWord:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CMapPtrToWord:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMapPtrToWord:: işleci \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map içine bir öğe ekler — için işleç değiştirme `SetAt` .|

## <a name="remarks"></a>Açıklamalar

`CMapWordToPtr`çalışma zamanı türü erişimini ve bir nesneye dökümünü desteklemek için IMPLEMENT_DYNAMIC makrosunu ekler `CDumpContext` . Tek tek harita öğelerinin dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Sözcüğe işaretçi eşlemeleri serileştirilemiyor.

Bir `CMapPtrToWord` nesne silindiğinde veya öğeleri kaldırıldığında, işaretçiler ve sözcükler kaldırılır. Anahtar işaretçilerin başvurduğu varlıklar kaldırılmaz.

Hakkında daha fazla bilgi için `CMapPtrToWord` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToWord`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
