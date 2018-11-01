---
title: CRBMultiMap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: f421848a87ea3cc38309e85eb39c9453530ce4fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659101"
---
# <a name="crbmultimap-class"></a>CRBMultiMap sınıfı

Bu sınıf, her anahtar Red-siyah bir ikili Ağacı'nı kullanarak birden fazla değer ile ilişkilendirilebilir izin veren bir eşleme yapısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar öğe türü.

*V*<br/>
Değer öğe türü.

*KTraits*<br/>
Kopyalamak veya taşımak temel öğeleri için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.

*VTraits*<br/>
Kopyalamak veya taşımak değeri öğeleri için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Oluşturucu.|
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Verilen anahtarla ilk öğenin konumunu bulmak için bu yöntemi çağırın.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Verilen anahtarla ilişkili değeri almak için bu yöntemi çağırın ve konum değerini güncelleştirin.|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Verilen anahtarla ilişkili öğenin almak için bu yöntemi çağırın ve konum değerini güncelleştirin.|
|[CRBMultiMap::Insert](#insert)|Haritayı bir öğe çifti eklemek için bu yöntemi çağırın.|
|[CRBMultiMap::RemoveKey](#removekey)|Tüm belirli bir anahtarın anahtar/değer öğeleri kaldırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CRBMultiMap` sıralı bir dizi temel öğeleri ve değerleri yönetme, belirli bir türü, eşleme bir dizi için destek sağlar. Farklı [CRBMap](../../atl/reference/crbmap-class.md) sınıfı, her anahtar ilişkilendirilebilir ile birden fazla değer.

Öğeleri (bir anahtar ve değerden oluşan) bir ikili ağaç biçiminde depolanan kullanarak yapı [CRBMultiMap::Insert](#insert) yöntemi. Öğeleri kullanılarak kaldırılabilir [CRBMultiMap::RemoveKey](#removekey) yöntemi belirtilen bir anahtarla eşleşen tüm öğeleri siler.

Ağacının çapraz geçişi yapılan olası yöntemleriyle gibi [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), ve [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Erişim anahtarı başına büyük olasılıkla birden çok değer olası kullanarak [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), ve [CRBMultiMap::GetNextWithKey ](#getnextwithkey) yöntemleri. Örneğin bakın [CRBMultiMap::CRBMultiMap](#crbmultimap) uygulamada bunun bir gösterim.

*KTraits* ve *VTraits* kopyalama veya öğeleri taşımak için gerekli olan herhangi bir ek kod içeren nitelikleri sınıflar parametrelerdir.

`CRBMultiMap` türetilen [CRBTree](../../atl/reference/crbtree-class.md), kırmızı-siyah algoritmasını kullanarak bir ikili ağacı uygular. Alternatif `CRBMultiMap` ve `CRBMap` tarafından sunulan [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı. Öğeleri yalnızca az sayıda depolanacak gerektiğinde kullanmayı [CSimpleMap](../../atl/reference/csimplemap-class.md) bunun yerine sınıf.

Çeşitli koleksiyon sınıflarını ve özelliklerini ve performans özelliklerini daha eksiksiz bir açıklaması için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="crbmultimap"></a>  CRBMultiMap::CRBMultiMap

Oluşturucu.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

*NBlockSize* parametre gerektiğinde yeni bir öğe ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır. Varsayılan bir kerede 10 öğe için bir alan ayırın.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

##  <a name="dtor"></a>  CRBMultiMap:: ~ CRBMultiMap

Yıkıcı.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

##  <a name="findfirstwithkey"></a>  CRBMultiMap::FindFirstWithKey

Verilen anahtarla ilk öğenin konumunu bulmak için bu yöntemi çağırın.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bulunacak öğe tanımlayan anahtar belirtir.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa, NULL Aksi halde, anahtar/değer ilk öğenin KONUMUNU döndürür.

### <a name="remarks"></a>Açıklamalar

Bir anahtar olarak `CRBMultiMap` bir veya daha fazla ilişkili değerlere sahip olabilir. Bu yöntem, belirli bir anahtar ile ilişkili konumu değerini (Bu aslında tek değer olabilir) ilk sağlar. Döndürülen konum değeri ile sonra kullanılabilir [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) veya [CRBMultiMap::GetNextWithKey](#getnextwithkey) değeri elde etmek ve konumu güncelleştirin.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

Örneğin bakın [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="getnextvaluewithkey"></a>  CRBMultiMap::GetNextValueWithKey

Verilen anahtarla ilişkili değeri almak için bu yöntemi çağırın ve konum değerini güncelleştirin.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Ya da bir çağrı ile elde edilen konum değeri [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap::GetNextWithKey](#getnextwithkey), veya önceki bir çağrı `GetNextValueWithKey`.

*Anahtarı*<br/>
Bulunacak öğe tanımlayan anahtar belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili bir öğe çifti döndürür.

### <a name="remarks"></a>Açıklamalar

Konum değerini sonraki anahtarıyla ilişkilendirilmiş değeri gösterecek şekilde güncelleştirilir. Daha fazla değer varsa, konum değeri NULL olarak ayarlanır.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

Örneğin bakın [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="getnextwithkey"></a>  CRBMultiMap::GetNextWithKey

Verilen anahtarla ilişkili öğenin almak için bu yöntemi çağırın ve konum değerini güncelleştirin.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Ya da bir çağrı ile elde edilen konum değeri [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), veya önceki bir çağrı `GetNextWithKey`.

*Anahtarı*<br/>
Bulunacak öğe tanımlayan anahtar belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sonraki döndürür [CRBTree::CPair sınıfı](crbtree-class.md#cpair_class) verilen anahtarla ilişkili öğe.

### <a name="remarks"></a>Açıklamalar

Konum değerini sonraki anahtarıyla ilişkilendirilmiş değeri gösterecek şekilde güncelleştirilir. Daha fazla değer varsa, konum değeri NULL olarak ayarlanır.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

##  <a name="insert"></a>  CRBMultiMap::Insert

Haritayı bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Eklenecek anahtar değeri `CRBMultiMap` nesne.

*value*<br/>
Eklenecek değer `CRBMultiMap` nesnesi ile ilişkili *anahtar*.

### <a name="return-value"></a>Dönüş Değeri

Anahtar/değer öğe çiftinin konumunu döndürür `CRBMultiMap` nesne.

### <a name="remarks"></a>Açıklamalar

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

Örneğin bakın [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="removekey"></a>  CRBMultiMap::RemoveKey

Tüm belirli bir anahtarın anahtar/değer öğeleri kaldırmak için bu yöntemi çağırın.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Silinecek öğeyi/öğeleri tanımlayan anahtar belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili değerler sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

`RemoveKey` eşleşen bir anahtara sahip tüm anahtar/değer öğeleri siler *anahtar*.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

Örneğin bakın [CRBMultiMap::CRBMultiMap](#crbmultimap).

## <a name="see-also"></a>Ayrıca Bkz.

[CRBTree Sınıfı](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap Sınıfı](../../atl/reference/catlmap-class.md)<br/>
[CRBMap Sınıfı](../../atl/reference/crbmap-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
