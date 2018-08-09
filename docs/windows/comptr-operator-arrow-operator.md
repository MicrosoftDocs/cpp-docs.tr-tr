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
ms.openlocfilehash: 1530f7998f2597aeb2fe46dba09f4844b471cd93
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644836"
---
# <a name="comptroperator-gt-operator"></a>ComPtr::operator -&gt; işleci
Geçerli bir şablon parametresi tarafından belirtilen tür için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli şablon tür adıyla belirtilen türün işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yardımcı işlevi, gereksiz yük STDMETHOD makrosu kullanarak neden olunan kaldırır. Bu işlev yapar `IUnknown` türleri **özel** yerine **sanal**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)