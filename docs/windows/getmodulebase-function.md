---
title: GetModuleBase işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 403330097f1428ee0d7650f5931aef1621f61b11
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612607"
---
# <a name="getmodulebase-function"></a>GetModuleBase İşlevi
Alır bir [ModuleBase](../windows/modulebase-class.md) işaretçi başvuru sayısını artırma ve azaltma için sağlayan bir [RuntimeClass](../windows/runtimeclass-class.md) nesne.
  
## <a name="syntax"></a>Sözdizimi
  
```cpp
inline Details::ModuleBase* GetModuleBase() throw()  
```
  
## <a name="return-value"></a>Dönüş Değeri
 Bir işaretçi bir `ModuleBase` nesne.
  
## <a name="remarks"></a>Açıklamalar
 Bu işlev artırmak ve azaltma için dahili olarak kullanılır Nesne başvurusu sayar.
  
 Bu işlev çağırarak başvuru sayısı denetlemek için kullanabileceğiniz [Modulebase::ıncrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) ve [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md).
  
## <a name="requirements"></a>Gereksinimler
 **Başlık:** implements.h
  
 **Namespace:** Microsoft::WRL
  
## <a name="see-also"></a>Ayrıca Bkz.
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)