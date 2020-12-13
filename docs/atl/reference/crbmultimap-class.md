---
description: 'Daha fazla bilgi edinin: CRBMultiMap sınıfı'
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
ms.openlocfilehash: 8dfe644521cb7ec4135c5c1f71d36371ac1706ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141030"
---
# <a name="crbmultimap-class"></a>CRBMultiMap sınıfı

Bu sınıf, Red-Black bir ikili ağaç kullanarak her bir anahtarın birden fazla değerle ilişkilendirilebilen bir eşleme yapısını temsil eder.

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
Değer öğesi türü.

*Knitelikler*<br/>
Anahtar öğelerini kopyalamak veya taşımak için kullanılan kod. Daha fazla ayrıntı için bkz. [Celementnitelikler sınıfı](../../atl/reference/celementtraits-class.md) .

*Sanal nitelikler*<br/>
Değer öğelerini kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRBMultiMap:: CRBMultiMap](#crbmultimap)|Oluşturucu.|
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRBMultiMap:: FindFirstWithKey](#findfirstwithkey)|Belirli bir anahtara sahip ilk öğenin konumunu bulmak için bu yöntemi çağırın.|
|[CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)|Verilen bir anahtarla ilişkili değeri almak için bu yöntemi çağırın ve konum değerini güncelleştirin.|
|[CRBMultiMap:: GetNextWithKey](#getnextwithkey)|Verilen bir anahtarla ilişkili öğeyi almak için bu yöntemi çağırın ve konum değerini güncelleştirin.|
|[CRBMultiMap:: INSERT](#insert)|Haritaya bir öğe çifti eklemek için bu yöntemi çağırın.|
|[CRBMultiMap:: RemoveKey](#removekey)|Verilen bir anahtarın tüm anahtar/değer öğelerini kaldırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CRBMultiMap` verilen herhangi bir türdeki bir eşleme dizisi için destek sağlar, sıralı anahtar öğe ve değer dizisini yönetebilir. [CRBMap](../../atl/reference/crbmap-class.md) sınıfının aksine, her anahtar birden fazla değerle ilişkilendirilebilir.

Öğeler (bir anahtar ve bir değerden oluşan), [CRBMultiMap:: INSERT](#insert) yöntemi kullanılarak bir ikili ağaç yapısında depolanır. Öğeler, verilen anahtarla eşleşen tüm öğeleri silen [CRBMultiMap:: RemoveKey](#removekey) yöntemi kullanılarak kaldırılabilir.

Ağaç geçişi, [CRBTree:: GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree:: GetNext](../../atl/reference/crbtree-class.md#getnext)ve [CRBTree:: GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)gibi yöntemlerle mümkün hale getirilir. CRBMultiMap:: [FindFirstWithKey](#findfirstwithkey), [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)ve [CRBMultiMap:: GetNextWithKey](#getnextwithkey) yöntemleri kullanılarak anahtar başına potansiyel olarak birden çok değere erişim olanağı vardır. Bu uygulamada bir çizim için [CRBMultiMap:: CRBMultiMap](#crbmultimap) örneğine bakın.

*Knitelikler* ve *vnitelikler* parametreleri, öğeleri kopyalamak veya taşımak için gereken ek kodu içeren nitelikler sınıflarıdır.

`CRBMultiMap` , Red-Black algoritmasını kullanarak bir ikili ağacı uygulayan [CRBTree](../../atl/reference/crbtree-class.md)' den türetilir. Ve için bir alternatifi, `CRBMultiMap` `CRBMap` [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı tarafından sunulur. Yalnızca az sayıda öğe depolanması gerektiğinde, bunun yerine [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfını kullanmayı düşünün.

Çeşitli koleksiyon sınıflarının ve bunların özelliklerinin ve performans özelliklerinin daha kapsamlı bir tartışması için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="crbmultimapcrbmultimap"></a><a name="crbmultimap"></a> CRBMultiMap:: CRBMultiMap

Oluşturucu.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

*NBlockSize* parametresi, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır. Varsayılan değer her seferinde 10 öğe için alan ayırır.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

## <a name="crbmultimapcrbmultimap"></a><a name="dtor"></a> CRBMultiMap:: ~ CRBMultiMap

Yok edicisi.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest bırakır.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

## <a name="crbmultimapfindfirstwithkey"></a><a name="findfirstwithkey"></a> CRBMultiMap:: FindFirstWithKey

Belirli bir anahtara sahip ilk öğenin konumunu bulmak için bu yöntemi çağırın.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bulunan öğeyi tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa ilk anahtar/değer öğesinin konumunu, aksi takdirde NULL değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İçindeki bir anahtarın `CRBMultiMap` bir veya daha fazla ilişkili değeri olabilir. Bu yöntem, söz konusu anahtarla ilişkili ilk değerin konum değerini (aslında tek bir değer olabilir) sağlar. Döndürülen konum değeri, değeri almak ve konumu güncelleştirmek için [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey) veya [CRBMultiMap:: GetNextWithKey](#getnextwithkey) ile kullanılabilir.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[CRBMultiMap:: CRBMultiMap](#crbmultimap)örneğine bakın.

## <a name="crbmultimapgetnextvaluewithkey"></a><a name="getnextvaluewithkey"></a> CRBMultiMap:: GetNextValueWithKey

Verilen bir anahtarla ilişkili değeri almak ve konum değerini güncelleştirmek için bu yöntemi çağırın.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum değeri, [CRBMultiMap:: FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap:: GetNextWithKey](#getnextwithkey)çağrısı veya önceki bir çağrısı ile elde edilen `GetNextValueWithKey` .

*anahtar*<br/>
Bulunan öğeyi tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili öğe çiftini döndürür.

### <a name="remarks"></a>Açıklamalar

Konum değeri, anahtarla ilişkili bir sonraki değere işaret etmek üzere güncelleştirilir. Daha fazla değer yoksa, konum değeri NULL olarak ayarlanır.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[CRBMultiMap:: CRBMultiMap](#crbmultimap)örneğine bakın.

## <a name="crbmultimapgetnextwithkey"></a><a name="getnextwithkey"></a> CRBMultiMap:: GetNextWithKey

Verilen bir anahtarla ilişkili öğeyi almak ve konum değerini güncelleştirmek için bu yöntemi çağırın.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum değeri, [CRBMultiMap:: FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap:: GetNextValueWithKey](#getnextvaluewithkey)çağrısı veya önceki bir çağrısı ile elde edilen `GetNextWithKey` .

*anahtar*<br/>
Bulunan öğeyi tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili sonraki [CRBTree:: CPair sınıf](crbtree-class.md#cpair_class) öğesini döndürür.

### <a name="remarks"></a>Açıklamalar

Konum değeri, anahtarla ilişkili bir sonraki değere işaret etmek üzere güncelleştirilir. Daha fazla değer yoksa, konum değeri NULL olarak ayarlanır.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

## <a name="crbmultimapinsert"></a><a name="insert"></a> CRBMultiMap:: INSERT

Haritaya bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Nesneye eklenecek anahtar değeri `CRBMultiMap` .

*değer*<br/>
Nesneye eklenecek değer `CRBMultiMap` , *anahtarla* ilişkili.

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki anahtar/değer öğesi çiftinin konumunu döndürür `CRBMultiMap` .

### <a name="remarks"></a>Açıklamalar

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[CRBMultiMap:: CRBMultiMap](#crbmultimap)örneğine bakın.

## <a name="crbmultimapremovekey"></a><a name="removekey"></a> CRBMultiMap:: RemoveKey

Verilen bir anahtarın tüm anahtar/değer öğelerini kaldırmak için bu yöntemi çağırın.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Silinecek öğe (ler) i tanımlayan anahtarı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili değerlerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

`RemoveKey`*anahtarla eşleşen bir* anahtara sahip olan tüm anahtar/değer öğelerini siler.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[CRBMultiMap:: CRBMultiMap](#crbmultimap)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CRBTree sınıfı](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap sınıfı](../../atl/reference/catlmap-class.md)<br/>
[CRBMap sınıfı](../../atl/reference/crbmap-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
