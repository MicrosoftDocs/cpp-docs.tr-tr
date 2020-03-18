---
title: CMapPtrToPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr::CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr::GetCount
- AFXCOLL/CMapPtrToPtr::GetHashTableSize
- AFXCOLL/CMapPtrToPtr::GetNextAssoc
- AFXCOLL/CMapPtrToPtr::GetSize
- AFXCOLL/CMapPtrToPtr::GetStartPosition
- AFXCOLL/CMapPtrToPtr::HashKey
- AFXCOLL/CMapPtrToPtr::InitHashTable
- AFXCOLL/CMapPtrToPtr::IsEmpty
- AFXCOLL/CMapPtrToPtr::Lookup
- AFXCOLL/CMapPtrToPtr::LookupKey
- AFXCOLL/CMapPtrToPtr::RemoveAll
- AFXCOLL/CMapPtrToPtr::RemoveKey
- AFXCOLL/CMapPtrToPtr::SetAt
helpviewer_keywords:
- CMapPtrToPtr [MFC], CMapPtrToPtr
- CMapPtrToPtr [MFC], GetCount
- CMapPtrToPtr [MFC], GetHashTableSize
- CMapPtrToPtr [MFC], GetNextAssoc
- CMapPtrToPtr [MFC], GetSize
- CMapPtrToPtr [MFC], GetStartPosition
- CMapPtrToPtr [MFC], HashKey
- CMapPtrToPtr [MFC], InitHashTable
- CMapPtrToPtr [MFC], IsEmpty
- CMapPtrToPtr [MFC], Lookup
- CMapPtrToPtr [MFC], LookupKey
- CMapPtrToPtr [MFC], RemoveAll
- CMapPtrToPtr [MFC], RemoveKey
- CMapPtrToPtr [MFC], SetAt
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
ms.openlocfilehash: b4ae511caab8278daf723bbcb8ffc5d57f5a1cd0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442675"
---
# <a name="cmapptrtoptr-class"></a>CMapPtrToPtr sınıfı

Void işaretçilerle anahtarlı void işaretçilerin eşlemelerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMapPtrToPtr : public CObject
```

## <a name="members"></a>Üyeler

`CMapPtrToPtr` üye işlevleri [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, üye işlevi özellikleri için `CMapStringToOb` başvuru belgelerini kullanabilirsiniz. İşlev parametresi veya dönüş değeri olarak `CObject` bir işaretçi Gördüğünüz her yerde, **void**için bir işaretçi yerine koyun. Bir işlev parametresi veya dönüş değeri olarak **char** için `CString` ya da **const** işaretçisi gördüğünüz her yerde, **void**için bir işaretçi yerine koyun.

`BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`

Örneğin, öğesine çevirir

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMapPtrToPtr:: CMapPtrToPtr](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMapPtrToPtr:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapPtrToPtr:: GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapPtrToPtr:: GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CMapPtrToPtr:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapPtrToPtr:: GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapPtrToPtr:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapPtrToPtr:: InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tabloyu başlatır.|
|[CMapPtrToPtr:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Boş eşleme koşulunu sınar (öğe yok).|
|[CMapPtrToPtr:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void işaretçi tuşuna bağlı olarak void bir işaretçi arar. İşaret ettiği varlık değil işaretçi değeri, anahtar karşılaştırması için kullanılır.|
|[CMapPtrToPtr:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru döndürür.|
|[CMapPtrToPtr:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapPtrToPtr:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CMapPtrToPtr:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMapPtrToPtr:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map içine bir öğe ekler — `SetAt`için işleç değiştirme.|

## <a name="remarks"></a>Açıklamalar

`CMapPtrToPtr`, çalışma zamanı tür erişimini desteklemek ve bir `CDumpContext` nesnesine dökümünü yapmak için IMPLEMENT_DYNAMIC makrosunu içerir. Tek tek harita öğelerinin (işaretçi değerleri) bir dökümünü almanız gerekiyorsa, döküm bağlamının derinliğini 1 veya daha büyük bir değere ayarlamanız gerekir.

İşaretçi arası haritalar serileştirilemiyor.

`CMapPtrToPtr` nesne silindiğinde veya öğeleri kaldırıldığında, başvurdukları varlıklara değil yalnızca işaretçiler kaldırılır.

`CMapPtrToPtr`hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
