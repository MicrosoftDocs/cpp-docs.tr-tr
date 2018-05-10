---
title: ComPtr::operator -&gt; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3cb3571207f328ad044ffd3f2f9b83bcebc7677e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperator-gt-operator"></a>ComPtr::operator -&gt; işleci
Geçerli şablon parametresi tarafından belirtilen tür için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli şablon tür adıyla belirtilen türün işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi STDMETHOD makrosu kullanımından kaynaklanan gereksiz yükünü kaldırır. Bu işlev IUnknown türleri sanal yerine özel hale getirir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)