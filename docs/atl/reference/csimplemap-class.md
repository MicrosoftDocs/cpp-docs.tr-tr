---
title: CSimpleMap Sınıfı
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
ms.openlocfilehash: b8650f36ac3d190207870616754dcd596cb7cc45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330807"
---
# <a name="csimplemap-class"></a>CSimpleMap Sınıfı

Bu sınıf basit bir eşleme dizisi için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>Parametreler

*Tkey*<br/>
Anahtar öğe türü.

*TVal*<br/>
Değer öğesi türü.

*TEqual*<br/>
Tür `T`öğeleri için eşitlik testini tanımlayan bir özellik nesnesi.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|Değer türü için typedef.|
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|Anahtar türü için typedef.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|Oluşturucu.|
|[CSimpleMap::~CSimpleMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleMap::Ekle](#add)|Harita dizisine anahtar ve ilişkili değer ekler.|
|[CSimpleMap::FindKey](#findkey)|Belirli bir anahtarı bulur.|
|[CSimpleMap::Findval](#findval)|Belirli bir değeri bulur.|
|[CSimpleMap::Getkeyat](#getkeyat)|Belirtilen anahtarı alır.|
|[CSimpleMap::GetSize](#getsize)|Eşleme dizisindeki giriş sayısını döndürür.|
|[CSimpleMap::GetValueat](#getvalueat)|Belirtilen değeri alır.|
|[CSimpleMap::Arama](#lookup)|Verilen anahtarla ilişkili değeri verir.|
|[CSimpleMap::Kaldır](#remove)|Bir anahtarı ve eşleşen değeri kaldırır.|
|[CSimpleMap::RemoveAll](#removeall)|Tüm anahtarları ve değerleri kaldırır.|
|[CSimpleMap::Removeat](#removeat)|Belirli bir anahtarı ve eşleşen değeri kaldırır.|
|[CSimpleMap::ReverseLookup](#reverselookup)|Verilen değerle ilişkili anahtarı döndürür.|
|[CSimpleMap::Setat](#setat)|Verilen anahtarla ilişkili değeri ayarlar.|
|[CSimpleMap::Setatindex](#setatindex)|Belirli anahtarı ve değeri ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CSimpleMap`belirli bir türdeki `T`basit bir eşleme dizisi için destek sağlar, sıralanmamış bir anahtar öğe dizisini ve bunların ilişkili değerlerini yönetir.

Parametre, `TEqual` türiki `T`öğe için bir eşitlik işlevi tanımlama aracı sağlar. [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)benzer bir sınıf oluşturarak, herhangi bir dizi için eşitlik testi davranışını değiştirmek mümkündür. Örneğin, bir işaretçi dizisiyle uğraşırken, eşitliği işaretçilerin başvurulan değerlerine bağlı olarak tanımlamak yararlı olabilir. Varsayılan uygulama **işleci kullanır==()**.

Hem `CSimpleMap` de [CSimpleArray](../../atl/reference/csimplearray-class.md) önceki ATL sürümleri ile uyumluluk için sağlanır ve daha eksiksiz ve verimli toplama uygulamaları [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAtlMap](../../atl/reference/catlmap-class.md)tarafından sağlanır.

ATL ve MFC'deki diğer harita koleksiyonlarının aksine, bu sınıf basit bir diziyle uygulanır ve arama aramaları doğrusal bir arama gerektirir. `CAtlMap`dizi çok sayıda öğe içerdiğinde kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

## <a name="csimplemapadd"></a><a name="add"></a>CSimpleMap::Ekle

Harita dizisine anahtar ve ilişkili değer ekler.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

*Val*<br/>
İlişkili değer.

### <a name="return-value"></a>Dönüş Değeri

Anahtar ve değer başarıyla eklenmiştirsa TRUE döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Her anahtar ve değer çifti eklendi, her biri için verilerin her zaman bitişik olarak depolandığından emin olmak için eşleme dizisi belleğinin serbest bırakılabilmesini ve yeniden ayrılmasına neden olur. Diğer bir deyişle, ikinci anahtar öğesi her zaman doğrudan bellek ve benzeri ilk anahtar öğesi izler.

## <a name="csimplemap_arrayelementtype"></a><a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType

Anahtar türü için bir typedef.

```
typedef TVal _ArrayElementType;
```

## <a name="csimplemap_arraykeytype"></a><a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType

Değer türü için bir typedef.

```
typedef TKey _ArrayKeyType;
```

## <a name="csimplemapcsimplemap"></a><a name="csimplemap"></a>CSimpleMap::CSimpleMap

Oluşturucu.

```
CSimpleMap();
```

### <a name="remarks"></a>Açıklamalar

Veri üyelerini ilk olarak karşılar.

## <a name="csimplemapcsimplemap"></a><a name="dtor"></a>CSimpleMap::~CSimpleMap

Yıkıcı.

```
~CSimpleMap();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="csimplemapfindkey"></a><a name="findkey"></a>CSimpleMap::FindKey

Belirli bir anahtarı bulur.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa anahtarın dizinini verir, aksi takdirde -1 döndürür.

## <a name="csimplemapfindval"></a><a name="findval"></a>CSimpleMap::Findval

Belirli bir değeri bulur.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>Parametreler

*Val*<br/>
Aranacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa değerin dizini döndürür, aksi takdirde -1 döndürür.

## <a name="csimplemapgetkeyat"></a><a name="getkeyat"></a>CSimpleMap::Getkeyat

Belirtilen dizindeki anahtarı alır.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Döndürülecek anahtarın dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından başvurulan anahtarı döndürür.

### <a name="remarks"></a>Açıklamalar

NIndex tarafından *nIndex* geçirilen dizin, iade değerinin anlamlı olması için geçerli olmalıdır.

## <a name="csimplemapgetsize"></a><a name="getsize"></a>CSimpleMap::GetSize

Eşleme dizisindeki giriş sayısını döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme dizisindeki giriş sayısını (anahtar ve değer bir giriştir) döndürür.

## <a name="csimplemapgetvalueat"></a><a name="getvalueat"></a>CSimpleMap::GetValueat

Belirli dizindeki değeri alır.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Döndürecek değerin dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından başvurulan değeri döndürür.

### <a name="remarks"></a>Açıklamalar

NIndex tarafından *nIndex* geçirilen dizin, iade değerinin anlamlı olması için geçerli olmalıdır.

## <a name="csimplemaplookup"></a><a name="lookup"></a>CSimpleMap::Arama

Verilen anahtarla ilişkili değeri verir.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

### <a name="return-value"></a>Dönüş Değeri

İlişkili değeri verir. Eşleşen anahtar bulunmazsa NULL döndürülür.

## <a name="csimplemapremove"></a><a name="remove"></a>CSimpleMap::Kaldır

Bir anahtarı ve eşleşen değeri kaldırır.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar ve eşleşen değer başarıyla kaldırıldıysa TRUE döndürür, aksi takdirde FALSE.

## <a name="csimplemapremoveall"></a><a name="removeall"></a>CSimpleMap::RemoveAll

Tüm anahtarları ve değerleri kaldırır.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Eşleme dizisi nesnesinden tüm anahtarları ve değerleri kaldırır.

## <a name="csimplemapremoveat"></a><a name="removeat"></a>CSimpleMap::Removeat

Belirtilen dizinde bir anahtar ve ilişkili değeri kaldırır.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kaldırılacak anahtar ve ilişkili değerin dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizin geçersiz bir dizin ise başarı doğru, FALSE döndürür.

## <a name="csimplemapreverselookup"></a><a name="reverselookup"></a>CSimpleMap::ReverseLookup

Verilen değerle ilişkili anahtarı döndürür.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>Parametreler

*Val*<br/>
Değer.

### <a name="return-value"></a>Dönüş Değeri

İlişkili anahtarı döndürür. Eşleşen anahtar bulunmazsa NULL döndürülür.

## <a name="csimplemapsetat"></a><a name="setat"></a>CSimpleMap::Setat

Verilen anahtarla ilişkili değeri ayarlar.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

*Val*<br/>
Atayacak yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa ve değer başarıyla değiştirildiyse TRUE döndürür, aksi takdirde FALSE.

## <a name="csimplemapsetatindex"></a><a name="setatindex"></a>CSimpleMap::Setatindex

Belirli bir dizinde anahtarı ve değeri ayarlar.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Dizin, anahtar ve değer eşleştirme değiştirmek için başvurur.

*anahtar*<br/>
Yeni anahtar.

*Val*<br/>
Yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Dizin geçerli değilse doğru döndürür, FALSE.

### <a name="remarks"></a>Açıklamalar

*NIndex*tarafından işaret edilen hem anahtarı hem de değeri güncelleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
