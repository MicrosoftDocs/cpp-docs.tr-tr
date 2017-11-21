---
title: "CDefaultCompareTraits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs: C++
helpviewer_keywords: CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a5a9a68bd220112d6e8065e273c47fdb7247096
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits sınıfı
Bu sınıf varsayılan öğesi karşılaştırma işlevleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Statik) Eşitlik için iki öğeleri karşılaştırmak için bu işlevini çağırın.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) Büyük ve küçük öğeyi belirlemek üzere bu işlevini çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir koleksiyon sınıfı nesnesinde depolanan öğeleri karşılaştırma için iki statik işlevler içerir. Bu sınıf tarafından kullanılan [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 Eşitlik için iki öğeleri karşılaştırmak için bu işlevini çağırın.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parametreler  
 `element1`  
 İlk öğe.  
  
 `element2`  
 İkinci öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri yanlış Aksi takdirde, eşitse true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan bu işlev eşitlik uygulamasıdır ( `==`) işleci. Basit veri türleri farklı nesneler için bu işlev geçersiz kılınması gerekebilir.  
  
##  <a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 Büyük ve küçük öğeyi belirlemek üzere bu işlevini çağırın.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parametreler  
 `element1`  
 İlk öğe.  
  
 `element2`  
 İkinci öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki tabloda temel bir tamsayı döndürür:  
  
|Koşul|Dönüş değeri|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını kullanan `==`,  **\<** , ve  **>**  işleçler. Basit veri türleri farklı nesneler için bu işlev geçersiz kılınması gerekebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
