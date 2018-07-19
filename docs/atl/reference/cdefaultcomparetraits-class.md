---
title: CDefaultCompareTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ed197cc1f18821b65c249ee15a7e75f54fc7a32
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884772"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits sınıfı
Bu sınıf, varsayılan öğe karşılaştırma işlevleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Koleksiyonda depolanacak veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Statik) Eşitlik için iki öğe karşılaştırmak için bu işlevi çağırın.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) Büyük ve daha az öğe belirlemek için bu işlevi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir koleksiyon sınıfı nesnesinde saklanan öğe karşılaştırmak için iki statik işlevler içerir. Bu sınıf tarafından kullanılan [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements  
 Eşitlik için iki öğe karşılaştırmak için bu işlevi çağırın.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parametreler  
 *element1*  
 İlk öğe.  
  
 *element2*  
 İkinci öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe yanlış Aksi takdirde, eşitse true döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını eşitliği olan (**==**) işleci. Basit veri türleri dışındaki nesneler için bu işlev geçersiz kılınması gerekebilir.  
  
##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered  
 Büyük ve daha az öğe belirlemek için bu işlevi çağırın.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parametreler  
 *element1*  
 İlk öğe.  
  
 *element2*  
 İkinci öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki tabloyu temel alan bir tamsayı döndürür:  
  
|Koşul|Dönüş değeri|  
|---------------|------------------|  
|*element1* < *element2*|<0|  
|*element1* == *element2*|0|  
|*element1* > *element2*|>0|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulamasını kullanan **==**, **\<**, ve **>** işleçleri. Basit veri türleri dışındaki nesneler için bu işlev geçersiz kılınması gerekebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
