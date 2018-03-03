---
title: "Derleyici Hatası C3457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3457
dev_langs:
- C++
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a85e746667371a625d137b0c21faec2172c1a382
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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