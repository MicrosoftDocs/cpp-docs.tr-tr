---
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
ms.openlocfilehash: afd9f017bb0fb9a95a0ed4fd135dcbd5ea4ddba2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284105"
---
# <a name="csimplemap-class"></a>CSimpleMap sınıfı

Bu sınıf, bir basit eşleme dizisi için destek sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>Parametreler

*TKey*<br/>
Anahtar öğe türü.

*TVal*<br/>
Değer öğe türü.

*TEqual*<br/>
Türü öğeler için eşitlik testi tanımlamak bir nitelik nesnesi `T`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|Değer türü için TypeDef.|
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|Anahtar türü için TypeDef.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|Oluşturucu.|
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMap::Add](#add)|Harita diziye bir anahtar ve ilişkili değer ekler.|
|[CSimpleMap::FindKey](#findkey)|Belirli bir anahtarın bulur.|
|[CSimpleMap::FindVal](#findval)|Belirli bir değeri bulur.|
|[CSimpleMap::GetKeyAt](#getkeyat)|Belirtilen anahtarı alır.|
|[CSimpleMap::GetSize](#getsize)|Girdi sayısı'eşleme diziyi döndürür.|
|[CSimpleMap::GetValueAt](#getvalueat)|Belirtilen değeri alır.|
|[CSimpleMap::Lookup](#lookup)|Verilen anahtarla ilişkili değeri döndürür.|
|[CSimpleMap::Remove](#remove)|Bir anahtar ve eşleşen değer kaldırır.|
|[CSimpleMap::RemoveAll](#removeall)|Tüm anahtarları ve değerleri kaldırır.|
|[CSimpleMap::RemoveAt](#removeat)|Bir özel anahtar ve eşleşen değer kaldırır.|
|[CSimpleMap::ReverseLookup](#reverselookup)|Verilen değer ile ilişkili anahtar döndürür.|
|[CSimpleMap::SetAt](#setat)|Verilen anahtarla ilişkili değeri ayarlar.|
|[CSimpleMap::SetAtIndex](#setatindex)|Özel anahtarı ve değeri ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CSimpleMap` herhangi bir türü bir basit eşleme dizisi için destek sağlar `T`, sırasız bir dizi temel öğeleri ve ilişkili değerleri yönetme.

Parametre `TEqual` tanımlamanın iki türü öğeler için bir eşitlik işlevi sağlar `T`. Bir sınıf benzer oluşturarak [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), verilen herhangi bir dizi için eşitlik testi davranışını değiştirmek mümkündür. Örneğin, bir işaretçiler dizisi ile ilgilenirken, bu değerlerin işaretçileri başvuran bağlı olarak bir eşitlik tanımlamak yararlı olabilir. Varsayılan uygulama yararlanan **operator==()**.

Her ikisi de `CSimpleMap` ve [CSimpleArray](../../atl/reference/csimplearray-class.md) önceki ATL uyumluluğunu serbest bırakır ve daha eksiksiz ve verimli koleksiyon uygulamaları tarafından sağlanan için sağlanan [CAtlArray](../../atl/reference/catlarray-class.md) ve [ CAtlMap](../../atl/reference/catlmap-class.md).

Diğer eşleme koleksiyonları ATL ve MFC aksine bu sınıf, basit bir diziyle uygulanır ve arama aramaları doğrusal arama gerektirir. `CAtlMap` dizi çok sayıda öğe içerdiğinde kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

##  <a name="add"></a>  CSimpleMap::Add

Harita diziye bir anahtar ve ilişkili değer ekler.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

*VAL*<br/>
İlişkili değer.

### <a name="return-value"></a>Dönüş Değeri

Anahtar ve değer Aksi halde başarıyla eklendi, FALSE ise TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Her anahtar ve değer çifti, serbest bırakılan ve için her biri için veriler her zaman bitişik depolanır emin olmak için bellek eşleme dizi nedenleri eklendi. Diğer bir deyişle, ikinci anahtar öğe her zaman doğrudan bellek ilk temel öğeyi vb. izler.

##  <a name="_arrayelementtype"></a>  CSimpleMap::_ArrayElementType

Anahtar türü için bir typedef.

```
typedef TVal _ArrayElementType;
```

##  <a name="_arraykeytype"></a>  CSimpleMap::_ArrayKeyType

Değer türü için bir typedef.

```
typedef TKey _ArrayKeyType;
```

##  <a name="csimplemap"></a>  CSimpleMap::CSimpleMap

Oluşturucu.

```
CSimpleMap();
```

### <a name="remarks"></a>Açıklamalar

Veri üyeleri başlatır.

##  <a name="dtor"></a>  CSimpleMap:: ~ CSimpleMap

Yıkıcı.

```
~CSimpleMap();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="findkey"></a>  CSimpleMap::FindKey

Belirli bir anahtarın bulur.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

İf anahtar dizini bulunamadı, döndürür, aksi takdirde -1 döndürür.

##  <a name="findval"></a>  CSimpleMap::FindVal

Belirli bir değeri bulur.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Aranacak değer.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa, değer dizinini yoksa -1 döndürür.

##  <a name="getkeyat"></a>  CSimpleMap::GetKeyAt

Belirtilen dizindeki bir anahtarı alır.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Anahtarı döndürülecek dizini.

### <a name="return-value"></a>Dönüş Değeri

Tarafından başvurulan anahtarını döndürür *nIndex*.

### <a name="remarks"></a>Açıklamalar

Geçirilen *nIndex* dönüş değeri anlamlı olacak şekilde geçerli olmalıdır.

##  <a name="getsize"></a>  CSimpleMap::GetSize

Girdi sayısı'eşleme diziyi döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme dizide (bir anahtarı ve değeri olan bir giriş) giriş sayısını döndürür.

##  <a name="getvalueat"></a>  CSimpleMap::GetValueAt

Belirli dizindeki değeri alır.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Döndürülecek değeri dizini.

### <a name="return-value"></a>Dönüş Değeri

Tarafından başvurulan değer döndürür *nIndex*.

### <a name="remarks"></a>Açıklamalar

Geçirilen *nIndex* dönüş değeri anlamlı olacak şekilde geçerli olmalıdır.

##  <a name="lookup"></a>  CSimpleMap::Lookup

Verilen anahtarla ilişkili değeri döndürür.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

### <a name="return-value"></a>Dönüş Değeri

İlişkili değer döndürür. Eşleşen bir anahtar varsa bulunamadı, NULL döndürülür.

##  <a name="remove"></a>  CSimpleMap::Remove

Bir anahtar ve eşleşen değer kaldırır.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar ve eşleşen değer, aksi halde başarıyla kaldırıldı, FALSE ise TRUE döndürür.

##  <a name="removeall"></a>  CSimpleMap::RemoveAll

Tüm anahtarları ve değerleri kaldırır.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Tüm anahtarları ve değerleri eşleme dizi nesnesinden kaldırır.

##  <a name="removeat"></a>  CSimpleMap::RemoveAt

Bir anahtarı ve belirtilen dizine ilişkili değeri kaldırır.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dizin anahtarı ve kaldırmak için ilişkili değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizin geçersiz bir dizin ise FALSE başarılı olduğunda TRUE değerini döndürür.

##  <a name="reverselookup"></a>  CSimpleMap::ReverseLookup

Verilen değer ile ilişkili anahtar döndürür.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Değer.

### <a name="return-value"></a>Dönüş Değeri

İlişkili anahtarını döndürür. Eşleşen bir anahtar varsa bulunamadı, NULL döndürülür.

##  <a name="setat"></a>  CSimpleMap::SetAt

Verilen anahtarla ilişkili değeri ayarlar.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar.

*VAL*<br/>
Atanacak yeni değer.

### <a name="return-value"></a>Dönüş Değeri

TRUE anahtar bulundu ve değer, aksi halde başarıyla değiştirildi, FALSE değerini döndürür.

##  <a name="setatindex"></a>  CSimpleMap::SetAtIndex

Belirtilen dizindeki bir anahtarı ve değeri ayarlar.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Anahtar ve değer çifti değiştirmek için başvuran dizin.

*anahtar*<br/>
Yeni anahtar.

*VAL*<br/>
Yeni değeri.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU başarılı, yanlış dizini geçerli değil, döndürür.

### <a name="remarks"></a>Açıklamalar

Hem anahtar hem de işaret ettiği değer güncelleştirmeleri *nIndex*.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
