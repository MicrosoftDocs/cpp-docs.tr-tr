---
description: 'Daha fazla bilgi edinin: CRBMap sınıfı'
title: CRBMap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
ms.openlocfilehash: 55d96bfd2c7b043bdbdc4c1ee1f329c9b77b9ca9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141056"
---
# <a name="crbmap-class"></a>CRBMap sınıfı

Bu sınıf, Red-Black bir ikili ağaç kullanarak bir eşleme yapısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMap:: CRBMap](#crbmap)|Oluşturucu.|
|[CRBMap:: ~ CRBMap](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRBMap:: Lookup](#lookup)|Nesne içindeki anahtarları veya değerleri aramak için bu yöntemi çağırın `CRBMap` .|
|[CRBMap:: RemoveKey](#removekey)|Bu yöntemi, anahtar verildiğinde nesnesinden bir öğeyi kaldırmak için çağırın `CRBMap` .|
|[CRBMap:: SetAt](#setat)|Haritaya bir öğe çifti eklemek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CRBMap` belirli bir türdeki bir eşleme dizisi için destek sağlar, sıralı bir anahtar öğeleri dizisi ve bunlarla ilişkili değerleri yönetebilir. Her anahtar yalnızca bir ilişkili değere sahip olabilir. Öğeler (bir anahtar ve bir değerden oluşan), [CRBMap:: SetAt](#setat) yöntemi kullanılarak bir ikili ağaç yapısında depolanır. Öğeler, verilen anahtar değerine sahip öğeyi silen [CRBMap:: RemoveKey](#removekey) yöntemi kullanılarak kaldırılabilir.

Ağaç geçişi, [CRBTree:: GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree:: GetNext](../../atl/reference/crbtree-class.md#getnext)ve [CRBTree:: GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)gibi yöntemlerle mümkün hale getirilir.

*Knitelikler* ve *vnitelikler* parametreleri, öğeleri kopyalamak veya taşımak için gereken ek kodu içeren nitelikler sınıflarıdır.

`CRBMap` , Red-Black algoritmasını kullanarak bir ikili ağacı uygulayan [CRBTree](../../atl/reference/crbtree-class.md)' den türetilir. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) , her anahtar için birden çok değere izin veren bir çeşitçdır. Bu, öğesinden türetilir `CRBTree` ve ile birçok özelliği paylaşır `CRBMap` .

Her ikisine de alternatif `CRBMap` olarak `CRBMultiMap` [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı tarafından sunulur. Yalnızca az sayıda öğe depolanması gerektiğinde, bunun yerine [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfını kullanmayı düşünün.

Çeşitli koleksiyon sınıflarının ve bunların özelliklerinin ve performans özelliklerinin daha kapsamlı bir tartışması için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a> CRBMap:: CRBMap

Oluşturucu.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

*NBlockSize* parametresi, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır. Varsayılan değer her seferinde 10 öğe için alan ayırır.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a> CRBMap:: ~ CRBMap

Yok edicisi.

```
~CRBMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest bırakır.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

## <a name="crbmaplookup"></a><a name="lookup"></a> CRBMap:: Lookup

Nesne içindeki anahtarları veya değerleri aramak için bu yöntemi çağırın `CRBMap` .

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan anahtarı belirtir.

*değer*<br/>
Aranan değeri alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Metodun ilk formu, anahtar bulunursa true, değilse false döndürür. İkinci ve üçüncü formlar, [CPair](crbtree-class.md#cpair_class)için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a> CRBMap:: RemoveKey

Bu yöntemi, anahtar verildiğinde nesnesinden bir öğeyi kaldırmak için çağırın `CRBMap` .

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kaldırmak istediğiniz öğe çiftine karşılık gelen anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa ve kaldırılırsa true, hata durumunda FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a> CRBMap:: SetAt

Haritaya bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Nesneye eklenecek anahtar değeri `CRBMap` .

*değer*<br/>
Nesneye eklenecek değer `CRBMap` .

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki anahtar/değer öğesi çiftinin konumunu döndürür `CRBMap` .

### <a name="remarks"></a>Açıklamalar

`SetAt` eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir. Anahtar bulunamazsa yeni bir anahtar/değer çifti oluşturulur.

Kullanılabilen diğer yöntemler hakkında bilgi için bkz. temel sınıf [CRBTree](../../atl/reference/crbtree-class.md) belgeleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CRBTree sınıfı](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap sınıfı](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap sınıfı](../../atl/reference/crbmultimap-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
