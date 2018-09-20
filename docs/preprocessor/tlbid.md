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
ms.openlocfilehash: f5bd922089bcf189c403a97679a593a985603a12
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446263"
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
 
[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)