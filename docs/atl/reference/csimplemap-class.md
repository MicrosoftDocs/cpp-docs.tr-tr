---
description: 'Daha fazla bilgi edinin: CSimpleMap sınıfı'
title: CSimpleMap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: 66640e3fcd325d59b82a10d98188a6fcd74ca79d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140627"
---
# <a name="csimplemap-class"></a>CSimpleMap sınıfı

Bu sınıf bir basit eşleme dizisi için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>Parametreler

*TKey*<br/>
Anahtar öğe türü.

*TVal*<br/>
Değer öğesi türü.

*TEqual*<br/>
Türü öğeler için eşitlik testini tanımlayarak bir nitelik nesnesi `T` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMap:: _ArrayElementType](#_arrayelementtype)|Değer türü için typedef.|
|[CSimpleMap:: _ArrayKeyType](#_arraykeytype)|Anahtar türü için typedef.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMap:: CSimpleMap](#csimplemap)|Oluşturucu.|
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMap:: Add](#add)|Map dizisine bir anahtar ve ilişkili değer ekler.|
|[CSimpleMap:: FindKey](#findkey)|Belirli bir anahtarı bulur.|
|[CSimpleMap:: FindVal](#findval)|Belirli bir değeri bulur.|
|[CSimpleMap:: GetKeyAt](#getkeyat)|Belirtilen anahtarı alır.|
|[CSimpleMap:: GetSize](#getsize)|Eşleme dizisindeki giriş sayısını döndürür.|
|[CSimpleMap:: Getvaluyemek](#getvalueat)|Belirtilen değeri alır.|
|[CSimpleMap:: Lookup](#lookup)|Verilen anahtarla ilişkili değeri döndürür.|
|[CSimpleMap:: Remove](#remove)|Bir anahtarı ve eşleşen değeri kaldırır.|
|[CSimpleMap:: RemoveAll](#removeall)|Tüm anahtarları ve değerleri kaldırır.|
|[CSimpleMap:: RemoveAt](#removeat)|Belirli bir anahtarı ve eşleşen değeri kaldırır.|
|[CSimpleMap:: Smarlookup](#reverselookup)|Verilen değerle ilişkili anahtarı döndürür.|
|[CSimpleMap:: SetAt](#setat)|Verilen anahtarla ilişkili değeri ayarlar.|
|[CSimpleMap:: SetAtIndex](#setatindex)|Belirli anahtarı ve değeri ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CSimpleMap``T`, bir dizi anahtar öğesi ve bunlarla ilişkili değerleri yöneten, belirli bir türün basit bir eşleme dizisi için destek sağlar.

Parametresi, `TEqual` türü iki öğe için eşitlik işlevi tanımlamayı sağlar `T` . [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)öğesine benzer bir sınıf oluşturarak, belirli bir dizi için eşitlik testinin davranışını değiştirmek mümkündür. Örneğin, bir işaretçiler dizisiyle ilgilenirken, işaretçiler başvurusunun değerlerine bağlı olarak eşitlik tanımlanması yararlı olabilir. Varsayılan uygulama **işleç = = ()** kullanır.

Hem `CSimpleMap` hem de [CSimpleArray](../../atl/reference/csimplearray-class.md) , önceki ATL sürümleriyle uyumluluk Için sağlanır ve [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAtlMap](../../atl/reference/catlmap-class.md)tarafından daha fazla tamamlanmış ve verimli koleksiyon uygulamalarıyla sunulmaktadır.

ATL ve MFC 'deki diğer harita koleksiyonlarının aksine, bu sınıf basit bir dizi ile uygulanır ve arama aramaları doğrusal bir arama gerektirir. `CAtlMap` dizi çok sayıda öğe içerdiğinde kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a> CSimpleMap:: Add

Map dizisine bir anahtar ve ilişkili değer ekler.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

*Acil*<br/>
İlişkili değer.

### <a name="return-value"></a>Dönüş Değeri

Anahtar ve değer başarıyla eklendiyse TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Eklenen her anahtar ve değer çifti, her zaman için verilerin her zaman depolandığından emin olmak için, eşleme dizisi belleğinin serbest bırakılmasına ve yeniden ayrılmasına neden olur. Diğer bir deyişle, ikinci anahtar öğesi her zaman bellekteki ilk anahtar öğeden hemen sonra ve bu şekilde devam eder.

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a> CSimpleMap:: _ArrayElementType

Anahtar türü için bir typedef.

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a> CSimpleMap:: _ArrayKeyType

Değer türü için bir typedef.

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a> CSimpleMap:: CSimpleMap

Oluşturucu.

```
CSimpleMap();
```

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır.

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a> CSimpleMap:: ~ CSimpleMap

Yok edicisi.

```
~CSimpleMap();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="csimplemapfindkey"></a><a name="findkey"></a> CSimpleMap:: FindKey

Belirli bir anahtarı bulur.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa anahtarın dizinini döndürür, aksi takdirde-1 döndürür.

## <a name="csimplemapfindval"></a><a name="findval"></a> CSimpleMap:: FindVal

Belirli bir değeri bulur.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>Parametreler

*Acil*<br/>
Aranacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa değerin dizinini döndürür, aksi takdirde-1 döndürür.

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a> CSimpleMap:: GetKeyAt

Belirtilen dizindeki anahtarı alır.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Döndürülecek anahtarın dizini.

### <a name="return-value"></a>Dönüş Değeri

*Nindex* tarafından başvurulan anahtarı döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değerinin anlamlı olması için *nIndex* tarafından geçirilen dizin geçerli olmalıdır.

## <a name="csimplemapgetsize"></a><a name="getsize"></a> CSimpleMap:: GetSize

Eşleme dizisindeki giriş sayısını döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme dizisindeki giriş (anahtar ve değer bir giriş) sayısını döndürür.

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a> CSimpleMap:: Getvaluyemek

Belirli dizindeki değeri alır.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Döndürülecek değerin dizini.

### <a name="return-value"></a>Dönüş Değeri

*Nindex* tarafından başvurulan değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değerinin anlamlı olması için *nIndex* tarafından geçirilen dizin geçerli olmalıdır.

## <a name="csimplemaplookup"></a><a name="lookup"></a> CSimpleMap:: Lookup

Verilen anahtarla ilişkili değeri döndürür.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

### <a name="return-value"></a>Dönüş Değeri

İlişkili değeri döndürür. Eşleşen anahtar bulunamazsa NULL döndürülür.

## <a name="csimplemapremove"></a><a name="remove"></a> CSimpleMap:: Remove

Bir anahtarı ve eşleşen değeri kaldırır.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar ve eşleşen değer başarıyla kaldırılmışsa TRUE, aksi takdirde FALSE döndürür.

## <a name="csimplemapremoveall"></a><a name="removeall"></a> CSimpleMap:: RemoveAll

Tüm anahtarları ve değerleri kaldırır.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Tüm anahtarları ve değerleri eşleme dizisi nesnesinden kaldırır.

## <a name="csimplemapremoveat"></a><a name="removeat"></a> CSimpleMap:: RemoveAt

Belirtilen dizinde bir anahtarı ve ilişkili değeri kaldırır.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak anahtarın ve ilişkili değerin dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, belirtilen dizin geçersiz bir dizin ise FALSE değerini döndürür.

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a> CSimpleMap:: Smarlookup

Verilen değerle ilişkili anahtarı döndürür.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>Parametreler

*Acil*<br/>
Değer.

### <a name="return-value"></a>Dönüş Değeri

İlişkili anahtarı döndürür. Eşleşen anahtar bulunamazsa NULL döndürülür.

## <a name="csimplemapsetat"></a><a name="setat"></a> CSimpleMap:: SetAt

Verilen anahtarla ilişkili değeri ayarlar.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

*Acil*<br/>
Atanacak yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa TRUE, değer başarıyla değiştirilmişse FALSE döndürür, aksi takdirde FALSE.

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a> CSimpleMap:: SetAtIndex

Belirtilen dizindeki anahtarı ve değeri ayarlar.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Değiştirilecek anahtar ve değer eşleştirmeye başvuran dizin.

*anahtar*<br/>
Yeni anahtar.

*Acil*<br/>
Yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, dizin geçerli değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Her iki anahtarı ve değeri *nindex* tarafından işaret ettiği şekilde güncelleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
