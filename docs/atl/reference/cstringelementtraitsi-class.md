---
title: "CStringElementTraitsI sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
dev_langs: C++
helpviewer_keywords: CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f2a2cbe93826ed2cad5d33d50df119d0ff5cb298
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI sınıfı
Bu sınıf, koleksiyon sınıfı nesneleri depolanan dizeleri ilgili statik işlevler sağlar. Aşağıdakine benzer [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), ancak büyük küçük harf duyarlı karşılaştırmaları gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>  
class CStringElementTraitsI : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](#compareelements)|İki dize öğesi durumda farklar yoksayılıyor eşitliği karşılaştırmak için bu statik işlevini çağırın.|  
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Farkları durumda yoksayılıyor iki dize öğesi karşılaştırmak için bu statik işlevini çağırın.|  
|[CStringElementTraitsI::Hash](#hash)|Verilen dize öğesi için bir karma değer hesaplamak için bu statik işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir karma değer oluşturmak ve dizeleri karşılaştırma için statik işlevler sağlar. Bu işlevleri koleksiyon sınıfı dize tabanlı veri depolamak için kullandığınızda yararlıdır. Kullanım [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) olduğunda string nesneleri ile birlikte başvuru olarak ele alınabilir.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringElementTraitsI::CompareElements  
 İki dize öğesi durumda farklar yoksayılıyor eşitliği karşılaştırmak için bu statik işlevini çağırın.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk öğe dize.  
  
 `str2`  
 İkinci öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri yanlış Aksi takdirde, eşitse true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Karşılaştırma büyük/küçük harfe duyarsızdır.  
  
##  <a name="compareelementsordered"></a>CStringElementTraitsI::CompareElementsOrdered  
 Farkları durumda yoksayılıyor iki dize öğesi karşılaştırmak için bu statik işlevini çağırın.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str1`  
 İlk öğe dize.  
  
 `str2`  
 İkinci öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır dizeleri özdeş ise, < 0 ise `str1` olan değerinden `str2`, veya > 0 ise `str1` değerinden daha büyük `str2`. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmaları gerçekleştirmek için kullanılır.  

  
### <a name="remarks"></a>Açıklamalar  
 Karşılaştırma büyük/küçük harfe duyarsızdır.  
  
##  <a name="hash"></a>CStringElementTraitsI::Hash  
 Verilen dize öğesi için bir karma değer hesaplamak için bu statik işlevini çağırın.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Dize öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin içeriği kullanılarak hesaplanan bir karma değer döndürür.  
  
##  <a name="inargtype"></a>CStringElementTraitsI::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE  
 Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CStringElementTraits sınıfı](../../atl/reference/cstringelementtraits-class.md)
