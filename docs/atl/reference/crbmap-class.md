---
title: CRBMap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b32b21c8785bb5e28058c51f2345c5ffcb6de1f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364943"
---
# <a name="crbmap-class"></a>CRBMap sınıfı
Bu sınıf kırmızı siyah bir ikili ağacı kullanarak bir eşleme yapısını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar öğe türü.  
  
 *V*  
 Değer öğe türü.  
  
 `KTraits`  
 Kopyalama veya anahtar öğeleri taşıma için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.  
  
 `VTraits`  
 Kopyalama veya değer öğeleri taşıma için kullanılan kod.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBMap::CRBMap](#crbmap)|Oluşturucu.|  
|[CRBMap:: ~ CRBMap](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBMap::Lookup](#lookup)|Anahtarlar veya değerler aramak için bu yöntemi çağırın `CRBMap` nesnesi.|  
|[CRBMap::RemoveKey](#removekey)|Bir öğeyi kaldırmak için bu yöntemi çağırın `CRBMap` anahtarı verilen nesnesi.|  
|[CRBMap::SetAt](#setat)|Bir öğe çifti eşlemeye eklemek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRBMap` bir eşleme dizisi temel öğeleri ve ilişkili değerleri sıralı bir dizi yönetme, belirtilen her tür için destek sağlar. Her anahtar tek bir ilişkili değer olabilir. Öğeleri (bir anahtarı ve değeri oluşan) bir ikili ağacı depolanan yapısı, kullanarak [CRBMap::SetAt](#setat) yöntemi. Öğeleri kullanılarak kaldırılabilir [CRBMap::RemoveKey](#removekey) belirli anahtar değeri öğeyle siler yöntemi.  
  
 Ağaç geçiş yapılan olası yöntemleriyle gibi [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), ve [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).  
  
 `KTraits` Ve `VTraits` parametreleridir kopyalamak veya öğeleri taşımak için gereken ek kod içeren özellikler sınıfları.  
  
 `CRBMap` türetilmiş [CRBTree](../../atl/reference/crbtree-class.md), kırmızı siyah algoritmasını kullanarak bir ikili ağacı uygular. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) her anahtar için birden çok değer veren bir çeşitlemedir. Gelen çok türetilen `CRBTree`ve bu nedenle birçok özelliklerle paylaşım `CRBMap`.  
  
 Her ikisi de alternatif `CRBMap` ve `CRBMultiMap` tarafından sunulan [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı. Az sayıda öğesi depolanması gerektiğinde kullanmayı [CSimpleMap](../../atl/reference/csimplemap-class.md) yerine sınıfı.  
  
 Çeşitli koleksiyon sınıfları, özellikleri ve performans özelliklerini daha eksiksiz bir tartışma için bkz [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
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
 `nBlockSize`  
 Blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 `nBlockSize` Parametresi yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır. Varsayılan bir kerede 10 öğeler için alan ayırın.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="dtor"></a>  CRBMap:: ~ CRBMap  
 Yok Edicisi.  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
##  <a name="lookup"></a>  CRBMap::Lookup  
 Anahtarlar veya değerler aramak için bu yöntemi çağırın `CRBMap` nesnesi.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bakılacak öğesi tanımlayan anahtarını belirtir.  
  
 *value*  
 Değişken, aranan yukarı değerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yönteminin ilk form anahtar, aksi takdirde false bulunursa true değerini döndürür. İkinci ve üçüncü forms bir işaretçi döndürmek bir [CPair](crbtree-class.md#cpair_class).  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="removekey"></a>  CRBMap::RemoveKey  
 Bir öğeyi kaldırmak için bu yöntemi çağırın `CRBMap` anahtarı verilen nesnesi.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Kaldırmak istediğiniz öğe çiftine karşılık gelen anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar bulundu ve kaldırıldı, başarısız olduğunda false ise true, aksi durumda değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="setat"></a>  CRBMap::SetAt  
 Bir öğe çifti eşlemeye eklemek için bu yöntemi çağırın.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar değeri eklemek için `CRBMap` nesnesi.  
  
 *value*  
 Eklenecek değer `CRBMap` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar/değer öğesi çifti konumunu döndürür `CRBMap` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetAt` eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır. Anahtar bulunamazsa yeni bir anahtar/değer çifti oluşturulur.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRBTree sınıfı](../../atl/reference/crbtree-class.md)   
 [CAtlMap sınıfı](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap sınıfı](../../atl/reference/crbmultimap-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
