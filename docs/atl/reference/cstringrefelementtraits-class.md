---
title: CStringRefElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 967ae999811e829ae7a890d367a6cdc16fb28239
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880495"
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits sınıfı
Bu sınıf, koleksiyon sınıfı nesnelerini içinde depolanan dizeleri ilgili statik işlevler sağlar. Dize nesnelerinin, başvuru olarak ile dağıtılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Koleksiyonda depolanacak veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Eşitlik için iki dize öğeleri Karşılaştırılacak statik bu işlevi çağırın.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|İki dize öğe Karşılaştırılacak statik bu işlevi çağırın.|  
|[CStringRefElementTraits::Hash](#hash)|Verilen dize öğesi için bir karma değeri hesaplamak için statik bu işlevi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, dizeleri karşılaştırmak ve bir karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için koleksiyon sınıfı kullanıldığında yararlıdır. Farklı [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) ve [Cstringelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` neden `CString` olarak geçirilecek bağımsız değişkenleri **const** `CString&` başvuruyor.  
  
 Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="compareelements"></a>  CStringRefElementTraits::CompareElements  
 Eşitlik için iki dize öğeleri Karşılaştırılacak statik bu işlevi çağırın.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *element1*  
 İlk dize öğesi.  
  
 *element2*  
 İkinci dize öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe yanlış Aksi takdirde, eşitse true döndürür.  
  
##  <a name="compareelementsordered"></a>  CStringRefElementTraits::CompareElementsOrdered  
 İki dize öğe Karşılaştırılacak statik bu işlevi çağırın.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *str1*  
 İlk dize öğesi.  
  
 *str2*  
 İkinci dize öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizeler aynıysa sıfır, < 0, *str1* olduğu küçüktür *str2*, veya > 0 ise *str1* büyüktür *str2*. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmalar yapmak için kullanılır.  
  
##  <a name="hash"></a>  CStringRefElementTraits::Hash  
 Verilen dize öğesi için bir karma değeri hesaplamak için statik bu işlevi çağırın.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *str*  
 Dize öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizenin içeriklerini kullanarak hesaplanan bir karma değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
