---
title: CStringElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ddce07ed7f79c167d4cf819b85de1484346bba93
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363991"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits sınıfı
Bu sınıf, depolama koleksiyon sınıfları tarafından kullanılan statik işlevler sağlar `CString` nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Statik) Eşitlik için iki dize öğeleri karşılaştırmak için bu işlevini çağırın.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) İki dize öğesi karşılaştırmak için bu işlevini çağırın.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Statik) Kopyalamak için bu işlevi çağırmak `CString` bir koleksiyon sınıfı nesnesinde depolanan öğeler.|  
|[CStringElementTraits::Hash](#hash)|(Statik) Verilen dize öğesi için bir karma değer hesaplamak için bu işlevini çağırın.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statik) Konumunu değiştirmek için bu işlevi çağırmak `CString` bir koleksiyon sınıfı nesnesinde depolanan öğeler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir karma değer oluşturma ve kopyalama, taşıma ve dizeleri karşılaştırma için statik işlevler sağlar. Bu işlevleri koleksiyon sınıfı dize tabanlı veri depolamak için kullandığınızda yararlıdır. Kullanım [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) duyarlı karşılaştırmalar zaman gereklidir. Kullanım [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) olduğunda string nesneleri ile başvuru olarak ele alınabilir.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cstringt.h  
  
##  <a name="compareelements"></a>  CStringElementTraits::CompareElements  
 Eşitlik için iki dize öğeleri karşılaştırmak için bu statik işlevini çağırın.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk öğe dize.  
  
 `str2`  
 İkinci öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri yanlış Aksi takdirde, eşitse true döndürür.  
  
##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered  
 İki dize öğesi karşılaştırmak için bu statik işlevini çağırın.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk öğe dize.  
  
 `str2`  
 İkinci öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır dizeleri özdeş ise, < 0 ise `str1` olan değerinden `str2`, veya > 0 ise `str1` değerinden daha büyük `str2`. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmaları gerçekleştirmek için kullanılır.  

  
##  <a name="copyelements"></a>  CStringElementTraits::CopyElements  
 Kopyalamak için bu statik işlev çağrısı `CString` bir koleksiyon sınıfı nesnesinde depolanan öğeler.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDest`  
 Kopyalanan veriler alacak ilk öğe işaretçi.  
  
 `pSrc`  
 Kopyalamak için ilk öğe işaretçi.  
  
 `nElements`  
 Kopyalanacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak ve hedef öğeleri çakışmaması gerekir.  
  
##  <a name="hash"></a>  CStringElementTraits::Hash  
 Verilen dize öğesi için bir karma değer hesaplamak için bu statik işlevini çağırın.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Dize öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin içeriği kullanılarak hesaplanan bir karma değer döndürür.  
  
##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE  
 Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements  
 Taşıyabilir bu statik işlev çağrısı `CString` bir koleksiyon sınıfı nesnesinde depolanan öğeler.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDest`  
 Yeniden konumlandırılan veri alacak ilk öğe işaretçi.  
  
 `pSrc`  
 İşaretçi ilk öğesine taşıyabilir.  
  
 `nElements`  
 Taşıyabilir öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik işlev çağrılarını [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), çoğu veri türleri için yeterli olduğu. Taşınan nesne kendi üye işaretçileri içeriyorsa, bu statik işlev geçersiz kılınacak gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI sınıfı](../../atl/reference/cstringelementtraitsi-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
