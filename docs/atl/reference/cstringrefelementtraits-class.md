---
title: "CStringRefElementTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs: C++
helpviewer_keywords: CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 733fbfd1a215ecf9a19990e38d0d4f11be8bd560
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits sınıfı
Bu sınıf, koleksiyon sınıfı nesneleri depolanan dizeleri ilgili statik işlevler sağlar. String nesneleri ile başvuru olarak dağıtılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Eşitlik için iki dize öğeleri karşılaştırmak için bu statik işlevini çağırın.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|İki dize öğesi karşılaştırmak için bu statik işlevini çağırın.|  
|[CStringRefElementTraits::Hash](#hash)|Verilen dize öğesi için bir karma değer hesaplamak için bu statik işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir karma değer oluşturmak ve dizeleri karşılaştırma için statik işlevler sağlar. Bu işlevleri koleksiyon sınıfı dize tabanlı veri depolamak için kullandığınızda yararlıdır. Farklı [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) ve [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` neden `CString` olarak geçirilecek bağımsız değişkenler **const CString &** başvurur.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 Eşitlik için iki dize öğeleri karşılaştırmak için bu statik işlevini çağırın.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `element1`  
 İlk öğe dize.  
  
 `element2`  
 İkinci öğe dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri yanlış Aksi takdirde, eşitse true döndürür.  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 İki dize öğesi karşılaştırmak için bu statik işlevini çağırın.  
  
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
  
##  <a name="hash"></a>CStringRefElementTraits::Hash  
 Verilen dize öğesi için bir karma değer hesaplamak için bu statik işlevini çağırın.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Dize öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin içeriği kullanılarak hesaplanan bir karma değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
