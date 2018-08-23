---
title: tlbıd | Microsoft Docs
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
ms.openlocfilehash: 1ec0150e63209728cf2f02c854fe03702b8a45b4
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465504"
---
# <a name="tlbid"></a>tlbid
**C++ özgü**  
  
Birincil tür kitaplığı dışında kitaplıklarını yüklemek için sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
tlbid(number)  
```  
  
### <a name="parameters"></a>Parametreler  
*Sayı*  
Tür Kitaplığı'nda sayısını `filename`.  
  
## <a name="remarks"></a>Açıklamalar  
 
Birden çok tür kitaplıklarının tek bir DLL'nin, birincil tür kitaplığı dışında kitaplıkları kullanarak yüklemek mümkün içinde yerleşik olan, **tlbıd**.  
  
Örneğin:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
eşdeğerdir:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
**END C++ özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)