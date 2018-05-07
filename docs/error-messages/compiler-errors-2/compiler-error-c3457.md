---
title: Derleyici Hatası C3457 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3457
dev_langs:
- C++
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99621cfd4f1827763be8ec84d82871290a04652b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3457"></a>Derleyici Hatası C3457
'öznitelik': öznitelik adı olmayan bağımsız değişkenler desteklemiyor  
  
 Kaynak ek açıklama özniteliklerini CLR özel öznitelik veya derleyici öznitelikleri farklı olarak, yalnızca adlandırılmış bağımsız değişkenler destekler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3457 oluşturur.  
  
```  
#include "SourceAnnotations.h"  
[vc_attributes::Post( 1 )] int f();   // C3457  
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK  
```