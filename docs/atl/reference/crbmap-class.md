---
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
ms.openlocfilehash: e5dedb26544bb2755bc74894cf36a622f5141f89
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278130"
---
# <a name="crbmap-class"></a>CRBMap sınıfı

Bu sınıf, Red-siyah bir ikili Ağacı'nı kullanarak bir eşleme yapısını temsil eder.

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
Değer öğe türü.

*KTraits*<br/>
Kopyalamak veya taşımak temel öğeleri için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.

*VTraits*<br/>
Kopyalamak veya taşımak değeri öğeleri için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRBMap::CRBMap](#crbmap)|Oluşturucu.|
|[CRBMap:: ~ CRBMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRBMap::Lookup](#lookup)|Anahtarlar veya değerler aramak için bu yöntemi çağırın `CRBMap` nesne.|
|[CRBMap::RemoveKey](#removekey)|Bir öğeyi kaldırmak için bu yöntemi çağırın `CRBMap` anahtar nesnesi.|
|[CRBMap::SetAt](#setat)|Haritayı bir öğe çifti eklemek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CRBMap` sıralı bir dizi temel öğeleri ve ilişkili değerleri yönetme, belirli bir tür, eşleme bir dizi için destek sağlar. Her anahtar, ilişkili yalnızca bir değer olabilir. Öğeleri (bir anahtar ve değerden oluşan) bir ikili ağaç biçiminde depolanan kullanarak yapı [CRBMap::SetAt](#setat) yöntemi. Öğeleri kullanılarak kaldırılabilir [CRBMap::RemoveKey](#removekey) yöntemi belirtilen anahtar değere sahip öğe siler.

Ağacının çapraz geçişi yapılan olası yöntemleriyle gibi [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), ve [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).

*KTraits* ve *VTraits* kopyalama veya öğeleri taşımak için gerekli olan herhangi bir ek kod içeren nitelikleri sınıflar parametrelerdir.

`CRBMap` türetilen [CRBTree](../../atl/reference/crbtree-class.md), kırmızı-siyah algoritmasını kullanarak bir ikili ağacı uygular. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) her anahtar için birden çok değer veren bir çeşitlemedir. Bu çok türetilir `CRBTree`ve bu nedenle çoğu özelliklerle paylaşımları `CRBMap`.

Hem de alternatif `CRBMap` ve `CRBMultiMap` tarafından sunulan [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı. Öğeleri yalnızca az sayıda depolanacak gerektiğinde kullanmayı [CSimpleMap](../../atl/reference/csimplemap-class.md) bunun yerine sınıf.

Çeşitli koleksiyon sınıflarını ve özelliklerini ve performans özelliklerini daha eksiksiz bir açıklaması için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="crbmap"></a>  CRBMap::CRBMap

Oluşturucu.

```
explicit CRBMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

*NBlockSize* parametre gerektiğinde yeni bir öğe ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır. Varsayılan bir kerede 10 öğe için bir alan ayırın.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]

##  <a name="dtor"></a>  CRBMap:: ~ CRBMap

Yıkıcı.

```
~CRBMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

##  <a name="lookup"></a>  CRBMap::Lookup

Anahtarlar veya değerler aramak için bu yöntemi çağırın `CRBMap` nesne.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bakılacak öğeyi tanımlayan anahtar belirtir.

*value*<br/>
Değişken, aranan yukarı değerini alır.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem biçiminin anahtar, aksi takdirde false bulunursa true değerini döndürür. İkinci ve üçüncü formları için bir işaretçi döndürür bir [CPair](crbtree-class.md#cpair_class).

### <a name="remarks"></a>Açıklamalar

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]

##  <a name="removekey"></a>  CRBMap::RemoveKey

Bir öğeyi kaldırmak için bu yöntemi çağırın `CRBMap` anahtar nesnesi.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kaldırmak istediğiniz anahtar karşılık gelen bir öğe çifti.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunan ve kaldırılmış, başarısız olduğunda false ise true, aksi durumda değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]

##  <a name="setat"></a>  CRBMap::SetAt

Haritayı bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Eklenecek anahtar değeri `CRBMap` nesne.

*value*<br/>
Eklenecek değer `CRBMap` nesne.

### <a name="return-value"></a>Dönüş Değeri

Anahtar/değer öğe çiftinin konumunu döndürür `CRBMap` nesne.

### <a name="remarks"></a>Açıklamalar

`SetAt` eşleşen bir anahtar bulunursa, var olan öğenin yerini alır. Anahtar bulunamazsa yeni bir anahtar/değer çifti oluşturulur.

Temel sınıf için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CRBTree Sınıfı](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap Sınıfı](../../atl/reference/catlmap-class.md)<br/>
[CRBMultiMap Sınıfı](../../atl/reference/crbmultimap-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
