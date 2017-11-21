---
title: "Derleyici Hatası C3457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3457
dev_langs: C++
helpviewer_keywords: C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d2550bdaa8d070b046ab9dbab6b21b691eed6f49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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