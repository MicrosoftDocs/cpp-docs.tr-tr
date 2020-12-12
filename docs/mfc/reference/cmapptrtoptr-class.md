---
description: 'Daha fazla bilgi edinin: CMapPtrToPtr sınıfı'
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
ms.openlocfilehash: 3cc561f7420e9c3c7bc2b2f6460536a80d7ef7cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259545"
---
# <a name="cmapptrtoptr-class"></a>CMapPtrToPtr sınıfı

Void işaretçilerle anahtarlı void işaretçilerin eşlemelerini destekler.

## <a name="syntax"></a>Syntax

```
class CMapPtrToPtr : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri `CMapPtrToPtr` [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)sınıfının üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CMapStringToOb` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi işlev parametresi veya dönüş değeri olarak gördüğünüz her yerde, bir işaretçisi yerine **`void`** . `CString` **`const`** İşlev parametresi veya dönüş değeri olarak bir işaretçisi veya bir işaretçi Gördüğünüz her yerde **`char`** , bir işaretçisi yerine **`void`** .

`BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`

Örneğin, öğesine çevirir

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMapPtrToPtr:: CMapPtrToPtr](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
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

|Ad|Açıklama|
|----------|-----------------|
|[CMapPtrToPtr:: işleci \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map içine bir öğe ekler — için işleç değiştirme `SetAt` .|

## <a name="remarks"></a>Açıklamalar

`CMapPtrToPtr` çalışma zamanı türü erişimini ve bir nesneye dökümünü desteklemek için IMPLEMENT_DYNAMIC makrosunu ekler `CDumpContext` . Tek tek harita öğelerinin (işaretçi değerleri) bir dökümünü almanız gerekiyorsa, döküm bağlamının derinliğini 1 veya daha büyük bir değere ayarlamanız gerekir.

İşaretçi arası haritalar serileştirilemiyor.

Bir `CMapPtrToPtr` nesne silindiğinde veya öğeleri kaldırıldığında, başvurdukları varlıkların değil yalnızca işaretçiler kaldırılır.

Hakkında daha fazla bilgi için `CMapPtrToPtr` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
