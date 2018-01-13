---
title: "CRBMultiMap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
dev_langs: C++
helpviewer_keywords: CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79ef7fdd5799b01ec115befcd50bbe4625d48bea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crbmultimap-class"></a>CRBMultiMap sınıfı
Bu sınıf, her anahtar kırmızı siyah bir ikili ağacı kullanarak birden fazla değer ile ilişkilendirilebilir izin veren bir eşleme yapısı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Oluşturucu.|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Verilen anahtarla ilk öğenin konumunu bulmak için bu yöntemi çağırın.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Verilen anahtarla ilişkili değeri almak için bu yöntemi çağırın ve konum değeri güncelleştirin.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Verilen anahtarla ilişkili öğesini almak için bu yöntemi çağırın ve konum değerini güncelleştirin.|  
|[CRBMultiMap::Insert](#insert)|Bir öğe çifti eşlemeye eklemek için bu yöntemi çağırın.|  
|[CRBMultiMap::RemoveKey](#removekey)|Belirli bir anahtar için anahtar/değer öğeleri kaldırmak için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRBMultiMap`bir eşleme dizisi temel öğeleri ve değerleri sıralı bir dizi yönetme, belirtilen her tür için destek sağlar. Farklı [CRBMap](../../atl/reference/crbmap-class.md) sınıfı, her anahtar ilişkilendirilebilir ile birden fazla değer.  
  
 Öğeleri (bir anahtarı ve değeri oluşan) bir ikili ağacı depolanan yapısı, kullanarak [CRBMultiMap::Insert](#insert) yöntemi. Öğeleri kullanılarak kaldırılabilir [CRBMultiMap::RemoveKey](#removekey) verilen anahtar eşleşen tüm öğeleri siler yöntemi.  
  
 Ağaç geçiş yapılan olası yöntemleriyle gibi [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), ve [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Erişim anahtarı başına büyük olasılıkla birden çok değeri olası kullanarak [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), ve [CRBMultiMap::GetNextWithKey ](#getnextwithkey) yöntemleri. Örneğin bkz [CRBMultiMap::CRBMultiMap](#crbmultimap) bir çizimi bu uygulamada için.  
  
 `KTraits` Ve `VTraits` parametreleridir kopyalamak veya öğeleri taşımak için gereken ek kod içeren özellikler sınıfları.  
  
 `CRBMultiMap`türetilmiş [CRBTree](../../atl/reference/crbtree-class.md), kırmızı siyah algoritmasını kullanarak bir ikili ağacı uygular. Alternatif `CRBMultiMap` ve `CRBMap` tarafından sunulan [CAtlMap](../../atl/reference/catlmap-class.md) sınıfı. Az sayıda öğesi depolanması gerektiğinde kullanmayı [CSimpleMap](../../atl/reference/csimplemap-class.md) yerine sınıfı.  
  
 Çeşitli koleksiyon sınıfları, özellikleri ve performans özelliklerini daha eksiksiz bir tartışma için bkz [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap  
 Oluşturucu.  
  
```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 `nBlockSize` Parametresi yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır. Varsayılan bir kerede 10 öğeler için alan ayırın.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMultiMap:: ~ CRBMultiMap  
 Yok Edicisi.  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
##  <a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey  
 Verilen anahtarla ilk öğenin konumunu bulmak için bu yöntemi çağırın.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bulunacak öğe tanımlayan anahtarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar bulunursa, NULL Aksi takdirde ilk anahtar/değer öğenin KONUMUNU döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir anahtar `CRBMultiMap` bir veya daha fazla ilişkili değerlere sahip olabilir. Bu yöntem, belirli bir anahtar ile ilişkili konum değerini (olabilen aslında, tek değer) ilk sağlar. Döndürülen konum değeri ile daha sonra kullanılabilir [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) veya [CRBMultiMap::GetNextWithKey](#getnextwithkey) değeri elde etmek ve konumu güncelleştirmek için.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey  
 Verilen anahtarla ilişkili değeri almak için bu yöntemi çağırın ve konum değeri güncelleştirin.  
  
```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Her iki çağrısıyla elde konum değeri [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap::GetNextWithKey](#getnextwithkey), veya önceki bir çağrı `GetNextValueWithKey`.  
  
 `key`  
 Bulunacak öğe tanımlayan anahtarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen anahtarla ilişkili öğenin çifti döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Konum değerini anahtar ile ilişkili sonraki değeri işaret edecek şekilde güncelleştirilir. Daha fazla değer yoksa, konum değeri NULL olarak ayarlanır.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey  
 Verilen anahtarla ilişkili öğesini almak için bu yöntemi çağırın ve konum değerini güncelleştirin.  
  
```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Her iki çağrısıyla elde konum değeri [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) veya [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), veya önceki bir çağrı `GetNextWithKey`.  
  
 `key`  
 Bulunacak öğe tanımlayan anahtarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki döndürür [CRBTree::CPair sınıfı](crbtree-class.md#cpair_class) verilen anahtarla ilişkili öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 Konum değerini anahtar ile ilişkili sonraki değeri işaret edecek şekilde güncelleştirilir. Daha fazla değer yoksa, konum değeri NULL olarak ayarlanır.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
##  <a name="insert"></a>CRBMultiMap::Insert  
 Bir öğe çifti eşlemeye eklemek için bu yöntemi çağırın.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar değeri eklemek için `CRBMultiMap` nesnesi.  
  
 *value*  
 Eklenecek değer `CRBMultiMap` ile ilişkili nesne `key`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar/değer öğesi çifti konumunu döndürür `CRBMultiMap` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="removekey"></a>CRBMultiMap::RemoveKey  
 Belirli bir anahtar için anahtar/değer öğeleri kaldırmak için bu yöntemi çağırın.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Silinecek öğe tanımlayan anahtarını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen anahtarla ilişkili değerler sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `RemoveKey`eşleşen bir anahtara sahip tüm anahtar/değer öğeleri siler `key`.  
  
 Taban sınıfı için belgelere bakın [CRBTree](../../atl/reference/crbtree-class.md) kullanılabilir diğer yöntemler hakkında bilgi edinmek için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRBTree sınıfı](../../atl/reference/crbtree-class.md)   
 [CAtlMap sınıfı](../../atl/reference/catlmap-class.md)   
 [CRBMap sınıfı](../../atl/reference/crbmap-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
