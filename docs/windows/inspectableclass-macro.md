---
title: Inspectableclass makrosu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 922f7f74771125aed0122c408ef902da2569e5c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873777"
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