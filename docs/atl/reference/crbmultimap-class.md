---
title: CRBMultiMap Sınıfı
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
ms.openlocfilehash: 1e36bc267b3a539d2d1d4bf370b9cdc33828c760
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331428"
---
# <a name="crbmultimap-class"></a>CRBMultiMap Sınıfı

Bu sınıf, her anahtarın kırmızı-siyah ikili ağaç kullanarak birden fazla değerle ilişkilendirilemelerine olanak tanıyan bir eşleme yapısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>Parametreler

*Kahraman*<br/>
Anahtar öğe türü.

*V*<br/>
Değer öğesi türü.

*KTraits*<br/>
Anahtar öğeleri kopyalamak veya taşımak için kullanılan kod. Daha fazla bilgi için [CElementTraits Sınıfına](../../atl/reference/celementtraits-class.md) bakın.

*VTraits*<br/>
Değer öğelerini kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Oluşturucu.|
|[CRBMultiMap::~CRBMultiMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Belirli bir anahtarla ilk öğenin konumunu bulmak için bu yöntemi arayın.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Belirli bir anahtarla ilişkili değeri almak ve konum değerini güncelleştirmek için bu yöntemi arayın.|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Belirli bir anahtarla ilişkili öğeyi almak ve konum değerini güncelleştirmek için bu yöntemi arayın.|
|[CRBMultiMap::Ekle](#insert)|Eşmeye bir öğe çifti eklemek için bu yöntemi çağırın.|
|[CRBMultiMap::RemoveKey](#removekey)|Belirli bir anahtar için tüm anahtar/değer öğelerini kaldırmak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

`CRBMultiMap`herhangi bir türde bir eşleme dizisi için destek sağlar, anahtar öğeleri ve değerleri sıralı bir dizi yönetme. [CRBMap](../../atl/reference/crbmap-class.md) sınıfının aksine, her anahtar birden fazla değerle ilişkilendirilebilir.

Öğeler (anahtar ve bir değerden oluşan) [CRBMultiMap](#insert) kullanılarak ikili ağaç yapısında depolanır::Ekle yöntemi. Öğeler [CRBMultiMap::RemoveKey](#removekey) yöntemi kullanılarak kaldırılabilir, verilen anahtarla eşleşen tüm öğeleri siler.

Ağacın geçişi [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)ve [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)gibi yöntemlerle mümkün olur. [CrBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)ve [CRBMultiMap::GetNextWithKey](#getnextwithkey) yöntemleri kullanılarak anahtar başına birden fazla değere erişmek mümkündür. CrBMultiMap için örneğe [bakın:CRBMultiMap](#crbmultimap) uygulamada bunun bir örneği için.

*KTraits* ve *VTraits* parametreleri öğeleri kopyalamak veya taşımak için gerekli herhangi bir ek kod içeren özellikler sınıflarıdır.

`CRBMultiMap`Kırmızı-Siyah algoritmasını kullanarak ikili bir ağaç uygulayan [CRBTree'den](../../atl/reference/crbtree-class.md)türetilmiştir. `CRBMultiMap` [CAtlMap](../../atl/reference/catlmap-class.md) sınıfına alternatif olarak sunulur. `CRBMap` Yalnızca az sayıda öğenin depolanması gerektiğinde, bunun yerine [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfını kullanmayı düşünün.

Çeşitli toplama sınıfları ve özellikleri ve performans özellikleri hakkında daha eksiksiz bir tartışma için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap

Oluşturucu.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

*nBlockSize* parametresi, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır. Varsayılan değer, bir seferde 10 öğe için alan ayırır.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a>CRBMultiMap::~CRBMultiMap

Yıkıcı.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest sağlar.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey

Belirli bir anahtarla ilk öğenin konumunu bulmak için bu yöntemi arayın.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bulunacak öğeyi tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa ilk anahtar/değer öğesinin konumunu döndürür, aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir anahtar `CRBMultiMap` bir veya daha fazla ilişkili değerlere sahip olabilir. Bu yöntem, o anahtarla ilişkili ilk değerin konum değerini (aslında tek değer olabilir) sağlayacaktır. Döndürülen konum değeri daha sonra [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) veya [CRBMultiMap::GetNextWithKey](#getnextwithkey) değeri elde etmek ve konumu güncellemek için kullanılabilir.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[CRBMultiMap örneğine bakın:CRBMultiMap](#crbmultimap).

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey

Belirli bir anahtarla ilişkili değeri almak ve konum değerini güncelleştirmek için bu yöntemi arayın.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
CRBMultiMap'e yapılan bir çağrıyla elde edilen konum [değeri::FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap::GetNextWithKey](#getnextwithkey), ya da önceki bir arama `GetNextValueWithKey`.

*anahtar*<br/>
Bulunacak öğeyi tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili öğe çiftini döndürür.

### <a name="remarks"></a>Açıklamalar

Konum değeri, anahtarla ilişkili bir sonraki değere işaret etmek için güncelleştirilir. Başka değer yoksa, konum değeri NULL olarak ayarlanır.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[CRBMultiMap örneğine bakın:CRBMultiMap](#crbmultimap).

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey

Belirli bir anahtarla ilişkili öğeyi almak ve konum değerini güncelleştirmek için bu yöntemi arayın.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
CRBMultiMap'e yapılan bir çağrıyla elde edilen konum [değeri::FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), ya da önceki bir arama `GetNextWithKey`.

*anahtar*<br/>
Bulunacak öğeyi tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili sonraki [CRBTree::CPair Class](crbtree-class.md#cpair_class) öğesini döndürür.

### <a name="remarks"></a>Açıklamalar

Konum değeri, anahtarla ilişkili bir sonraki değere işaret etmek için güncelleştirilir. Başka değer yoksa, konum değeri NULL olarak ayarlanır.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

## <a name="crbmultimapinsert"></a><a name="insert"></a>CRBMultiMap::Ekle

Eşmeye bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
`CRBMultiMap` Nesneye eklenecek anahtar değer.

*Değer*<br/>
`CRBMultiMap` Nesneye eklenecek değer, *anahtarla*ilişkilidir.

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki anahtar/değer öğesi çiftinin `CRBMultiMap` konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[CRBMultiMap örneğine bakın:CRBMultiMap](#crbmultimap).

## <a name="crbmultimapremovekey"></a><a name="removekey"></a>CRBMultiMap::RemoveKey

Belirli bir anahtar için tüm anahtar/değer öğelerini kaldırmak için bu yöntemi arayın.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Silinecek öğe(ler)i tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili değer sayısını verir.

### <a name="remarks"></a>Açıklamalar

`RemoveKey`*anahtarla*eşleşen bir anahtara sahip tüm anahtar/değer öğelerini siler.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[CRBMultiMap örneğine bakın:CRBMultiMap](#crbmultimap).

## <a name="see-also"></a>Ayrıca bkz.

[CRBTree Sınıfı](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap Sınıfı](../../atl/reference/catlmap-class.md)<br/>
[CRBMap Sınıfı](../../atl/reference/crbmap-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
