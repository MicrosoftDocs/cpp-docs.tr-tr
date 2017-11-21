---
title: Inspectableclass makrosu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::InspectableClass
dev_langs: C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f9cb2ac0ef10492d226fee9ef40d95c18b4f3ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [RuntimeClass sınıfı](../windows/runtimeclass-class.md)