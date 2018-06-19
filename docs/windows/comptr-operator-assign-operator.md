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
ms.openlocfilehash: f4066db37de8a993802970784f09141352fef028
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871207"
---
# <a name="comptroperator-operator"></a>ComPtr::operator= İşleci
Bir değer için geçerli ComPtr atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `U`  
 Bir sınıf.  
  
 `other`  
 Bir tür ya da başka bir ComPtr işaretçi, başvuru ya da rvalue başvuru.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli ComPtr referansı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleç ilk sürümü boş bir değer için geçerli ComPtr atar.  
  
 Atama arabirim işaretçisi geçerli ComPtr arabirim işaretçisi ile aynı değilse ikinci bir sürümde geçerli ComPtr ikinci arabirim işaretçisi atanır.  
  
 Üçüncü sürümünde atama arabirim işaretçisi geçerli ComPtr atanır.  
  
 Arabirim işaretçisi atama değerinin geçerli ComPtr arabirim işaretçisi ile aynı değilse, dördüncü sürümünde geçerli ComPtr ikinci arabirim işaretçisi atanır.  
  
 Beşinci sürüm kopyalama işlecidir; bir ComPtr başvuru geçerli ComPtr atanır.  
  
 Kullanan bir kopya işleci taşıma semantiği altıncı sürümüdür; herhangi bir tür cast geçerli ComPtr atanan statik ise ComPtr bir rvalue başvuru.  
  
 Kullanan bir kopya işleci taşıma semantiği yedinci sürümüdür; rvalue başvuru türünde bir ComPtr için `U` statik sonra cast ve geçerli ComPtr atanmış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)