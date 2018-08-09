---
title: ComPtr::operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ff70348f2305a5c75515630a5b6b9e2937494b5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641284"
---
# <a name="comptroperator-operator"></a>ComPtr::operator= İşleci
Geçerli bir değer atar **ComPtr**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <typename U>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *U*  
 Bir sınıf.  
  
 *Diğer*  
 Bir işaretçi, başvuru veya bir tür veya başka bir rvalue başvurusunu **ComPtr**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir başvuru **ComPtr**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleç ilk sürümü geçerli boş bir değer atar **ComPtr**.  
  
 Atama arabirim işaretçisini geçerli aynı değilse, İkinci Sürüm **ComPtr** arabirim işaretçisini, ikinci arabirim işaretçisi için geçerli atandığı **ComPtr**.  
  
 Üçüncü sürümünde geçerli atama arabirim işaretçisi atanır **ComPtr**.  
  
 Dördüncü sürümünde arabirim işaretçisi atama değerin geçerli aynı değilse **ComPtr** arabirim işaretçisini, ikinci arabirim işaretçisi için geçerli atandığı **ComPtr**.  
  
 Bir kopya işleci beşinci sürümüdür; bir başvuru bir **ComPtr** geçerli atanan **ComPtr**.  
  
 Taşıma semantiği kullanan bir kopya işlecine altıncı sürümüdür; rvalue başvurusuna bir **ComPtr** herhangi bir tür cast ve ardından geçerli atanan statikse **ComPtr**.  
  
 Taşıma semantiği kullanan bir kopya işlecine yedinci sürümüdür; rvalue başvurusuna bir **ComPtr** türü *U* olan statik as ardından ve geçerli atanan **ComPtr**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)