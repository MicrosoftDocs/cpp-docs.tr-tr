---
title: CRBMap Sınıfı
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
ms.openlocfilehash: 9e367ccc875eedf63e4f47018598662af2dfcf7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331405"
---
# <a name="crbmap-class"></a>CRBMap Sınıfı

Bu sınıf, Kırmızı-Siyah ikili ağaç kullanarak bir eşleme yapısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMap::CRBMap](#crbmap)|Oluşturucu.|
|[CRBMap::~CRBMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRBMap::Arama](#lookup)|`CRBMap` Nesnedeki anahtarları veya değerleri aramak için bu yöntemi arayın.|
|[CRBMap::RemoveKey](#removekey)|Anahtar verilen `CRBMap` bir öğeyi nesneden kaldırmak için bu yöntemi çağırın.|
|[CRBMap::Setat](#setat)|Eşmeye bir öğe çifti eklemek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CRBMap`sıralanmış bir anahtar öğe dizisini ve ilişkili değerlerini yöneten, belirli bir türdeki eşleme dizisi için destek sağlar. Her anahtarın yalnızca bir ilişkili değeri olabilir. Öğeler (anahtar ve bir değerden oluşan) [CRBMap::SetAt](#setat) yöntemi kullanılarak ikili ağaç yapısında depolanır. Öğeler [CRBMap::RemoveKey](#removekey) yöntemi kullanılarak kaldırılabilir, bu da öğeyi verilen anahtar değeriyle siler.

Ağacın geçişi [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)ve [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)gibi yöntemlerle mümkün olur.

*KTraits* ve *VTraits* parametreleri öğeleri kopyalamak veya taşımak için gerekli herhangi bir ek kod içeren özellikler sınıflarıdır.

`CRBMap`Kırmızı-Siyah algoritmasını kullanarak ikili bir ağaç uygulayan [CRBTree'den](../../atl/reference/crbtree-class.md)türetilmiştir. [CRBMultiMap,](../../atl/reference/crbmultimap-class.md) her anahtar için birden çok değer sağlayan bir varyasyondur. O da türetilmiştir `CRBTree`, ve `CRBMap`bu yüzden birçok özellik paylaşır .

Her ikisine `CRBMap` `CRBMultiMap` de bir alternatif ve [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı tarafından sunulmaktadır. Yalnızca az sayıda öğenin depolanması gerektiğinde, bunun yerine [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfını kullanmayı düşünün.

Çeşitli toplama sınıfları ve özellikleri ve performans özellikleri hakkında daha eksiksiz bir tartışma için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="crbmapcrbmap"></a><a name="crbmap"></a>CRBMap::CRBMap

Oluşturucu.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

*nBlockSize* parametresi, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır. Varsayılan değer, bir seferde 10 öğe için alan ayırır.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

## <a name="crbmapcrbmap"></a><a name="dtor"></a>CRBMap::~CRBMap

Yıkıcı.

```
~CRBMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest sağlar.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

## <a name="crbmaplookup"></a><a name="lookup"></a>CRBMap::Arama

`CRBMap` Nesnedeki anahtarları veya değerleri aramak için bu yöntemi arayın.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan anahtarı belirtir.

*Değer*<br/>
Aradeğerini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Yöntemin ilk biçimi anahtar bulunursa doğru döndürür, aksi takdirde yanlış. İkinci ve üçüncü formlar bir işaretçiyi [CPair'e](crbtree-class.md#cpair_class)döndürür.

### <a name="remarks"></a>Açıklamalar

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

## <a name="crbmapremovekey"></a><a name="removekey"></a>CRBMap::RemoveKey

Anahtar verilen `CRBMap` bir öğeyi nesneden kaldırmak için bu yöntemi çağırın.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kaldırmak istediğiniz öğe çiftine karşılık gelen anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunur ve kaldırılırsa, hata yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

## <a name="crbmapsetat"></a><a name="setat"></a>CRBMap::Setat

Eşmeye bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
`CRBMap` Nesneye eklenecek anahtar değer.

*Değer*<br/>
`CRBMap` Nesneye eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki anahtar/değer öğesi çiftinin `CRBMap` konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

`SetAt`eşleşen bir anahtar bulunursa varolan bir öğenin yerini alır. Anahtar bulunamazsa, yeni bir anahtar/değer çifti oluşturulur.

Mevcut diğer yöntemler hakkında bilgi için taban sınıf [CRBTree](../../atl/reference/crbtree-class.md) için belgelere bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CRBTree Sınıfı](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap Sınıfı](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap Sınıfı](../../atl/reference/crbmultimap-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
