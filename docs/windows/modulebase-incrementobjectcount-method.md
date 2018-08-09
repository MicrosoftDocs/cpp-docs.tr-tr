---
title: Modulebase::ıncrementobjectcount yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
dev_langs:
- C++
helpviewer_keywords:
- IncrementObjectCount method
ms.assetid: 2d70b472-684c-4bb7-8bab-09505cfcaf28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ee6c71ba6de195386cda78f2e44902c43523143
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011081"
---
# <a name="modulebaseincrementobjectcount-method"></a>ModuleBase::IncrementObjectCount Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
virtual long IncrementObjectCount() = 0;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önce Artım işlemi sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulandığında, modül tarafından izlenen nesne sayısını artırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ModuleBase sınıfı](../windows/modulebase-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)