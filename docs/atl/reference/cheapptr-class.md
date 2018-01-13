---
title: "CHeapPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs: C++
helpviewer_keywords: CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47fe8c0d7475c67228fd7335b1aa167ced237202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cheapptr-class"></a>CHeapPtr sınıfı
Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öbek üzerinde depolanması için nesne türü.  
  
 `Allocator`  
 Bellek ayırma kullanacak şekilde sınıfı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|Nesneleri depolamak için yığında bellek ayırmak için bu yöntemi çağırın.|  
|[CHeapPtr::Reallocate](#reallocate)|Yığın belleği yeniden tahsis etmek için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CHeapPtr`türetilmiş [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) ve varsayılan olarak CRT yordamları kullanır (içinde [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) ayırmak ve belleği boşaltmak için. Sınıf [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) yığın işaretçileri listesini oluşturmak için kullanılabilir. Ayrıca bkz. [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), COM bellek ayırma yordamları kullanır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="allocate"></a>CHeapPtr::Allocate  
 Nesneleri depolamak için yığında bellek ayırmak için bu yöntemi çağırın.  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nElements`  
 Ayrılacak bellek miktarını hesaplamak için kullanılan öğe sayısı. Varsayılan değer 1’dir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış bellek başarılı olduysa true değerini döndürür, başarısız olduğunda false.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayırıcı yordamları yığınındaki depolamak için yeterli bellek ayırmak için kullanılan *nElement* oluşturucuda tanımlanan bir tür nesneler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>CHeapPtr::CHeapPtr  
 Oluşturucu.  
  
```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Varolan bir yığın işaretçisi veya `CHeapPtr`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yığın işaretçi var olan bir işaretçi kullanarak isteğe bağlı olarak oluşturulabilir veya `CHeapPtr` nesnesi. Bu durumda, yeni `CHeapPtr` nesne yeni işaretçi ve kaynakları yönetmek için sorumluluk varsayar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>CHeapPtr::operator =  
 Atama işleci.  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Varolan bir `CHeapPtr` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir başvuru döndürür `CHeapPtr`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>CHeapPtr::Reallocate  
 Yığın belleği yeniden tahsis etmek için bu yöntemi çağırın.  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nElements`  
 Ayrılacak bellek miktarını hesaplamak için kullanılan öğeleri yeni sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış bellek başarılı olduysa true değerini döndürür, başarısız olduğunda false.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeapPtrBase sınıfı](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator sınıfı](../../atl/reference/ccrtallocator-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
