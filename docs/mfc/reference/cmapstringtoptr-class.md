---
title: CMapStringToPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToPtr
- AFXCOLL/CMapStringToPtr
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
dev_langs:
- C++
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
ms.assetid: 1ac11143-eb0a-4511-a662-2df0d1d9005b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc7d201ba32d0f7e3a4c860c6df117e9c74ae254
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055508"
---
# <a name="cmapstringtoptr-class"></a>CMapStringToPtr sınıfı

Anahtarlanan void işaretçilerin haritalarını destekler `CString` nesneleri.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToPtr : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CMapStringToPtr` sınıfın üye işlevleri için benzer [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CMapStringToOb` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir işlev parametre veya dönüş değeri olarak alternatif bir işaretçiye **void**.

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

Örneğin, için çevirir

`BOOL CMapStringToPtr::Lookup( LPCTSTR <key>, void*& <rValue> ) const;`

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
|[CMapStringToOb::operator [ ]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Haritayı bir öğe ekler; işleci alternatifi için `SetAt`.|

## <a name="remarks"></a>Açıklamalar

`CMapStringToPtr` ımplement_dynamıc makrosu, çalışma zamanı tür erişimi ve dökme için desteği kapsayan bir `CDumpContext` nesne. Tek tek harita öğelerine dökümü gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

Dize işaretçisine haritalar serileştirilemez.

Olduğunda bir `CMapStringToPtr` nesnesi silindiğinde veya ne zaman öğeleri kaldırılır, `CString` anahtar nesneleri ve sözcükler kaldırılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

