---
title: tlbid | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52cb9237537e151e699974fe91c5a7a99725513f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
  
 Son C++ özel  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)