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
ms.openlocfilehash: a02e20f2b87afc312c24683417f808d636c2757f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608962"
---
# <a name="inspectableclass-macro"></a>InspectableClass Makrosu
Çalışma zamanı sınıf adı ve güven düzeyini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
```  
  
### <a name="parameters"></a>Parametreler  
 *runtimeClassName*  
 Çalışma zamanı sınıfının tam metin adı.  
  
 *trustLevel*  
 Aşağıdakilerden birini [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) numaralandırılmış değerlerinin.  
  
## <a name="remarks"></a>Açıklamalar  
 **Inspectableclass** makrosu, yalnızca Windows çalışma zamanı türleri ile kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)