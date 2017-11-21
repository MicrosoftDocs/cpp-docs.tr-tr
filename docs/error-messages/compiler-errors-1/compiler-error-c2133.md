---
title: "Derleyici Hatası C2133 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2133
dev_langs: C++
helpviewer_keywords: C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c04452ec947adefa6b30928dc75de4edffc361fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2133"></a>Derleyici Hatası C2133
'tanımlayıcısı': Bilinmeyen boyutu  
  
 Boyutsuz dizi sınıfı, yapısı, UNION veya numaralandırma üyesi olarak bildirildi. /Za (ANSI C) seçeneğini boyutsuz üye dizileri izin vermiyor.  
  
 Aşağıdaki örnek C2133 oluşturur:  
  
```  
// C2133.cpp  
// compile with: /Za  
struct X {  
   int a[0];   // C2133 unsized array  
};  
```  
  
 Olası çözüm:  
  
```  
// C2133b.cpp  
// compile with: /c  
struct X {  
   int a[0];   // no /Za  
};  
```