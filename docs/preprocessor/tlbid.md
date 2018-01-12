---
title: tlbid | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tlbid
dev_langs: C++
helpviewer_keywords: tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 812b105fc02782b611b3f55061e448062dcd07c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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