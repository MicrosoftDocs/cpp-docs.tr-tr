---
title: Inspectableclass makrosu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ac1f84c76bb61d24ee25e8ca431e13620f6f85a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inspectableclass-macro"></a>InspectableClass Makrosu
Çalışma zamanı sınıf adı ve güven düzeyinde ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtimeClassName`  
 Çalışma zamanı sınıf tam metin adı.  
  
 `trustLevel`  
 Aşağıdakilerden birini [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) değerleri numaralandırılır.  
  
## <a name="remarks"></a>Açıklamalar  
 `InspectableClass` Makrosu yalnızca Windows çalışma zamanı türleriyle kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)