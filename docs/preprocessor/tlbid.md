---
title: tlbid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d651546733f42b1a714ac7a39992fa2d392c8fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="tlbid"></a>tlbid
**C++ özel**  
  
 Birincil tür kitaplığı dışında kitaplıkları yüklenmesini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `number`  
 Tür Kitaplığı'nda sayısı `filename`.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden çok tür kitaplıklarının tek DLL, birincil tür kitaplığı dışında kitaplıklarını kullanarak yük mümkün içinde yerleşik varsa `tlbid`.  
  
 Örneğin:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 eşdeğerdir:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)