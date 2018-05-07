---
title: Derleyici Uyarısı (düzey 1) C4364 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4364
dev_langs:
- C++
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb3bfb8075d618a6d2ea9b733b01d8b456fdc0e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4364"></a>Derleyici Uyarısı (düzey 1) C4364
\#derleme 'location(line_number) as_friend özniteliği; olmadan, daha önce görülen dosya' için kullanma uygulanmamış as_friend  
  
 A `#using` yönergesi verilen meta veri dosyası için yinelenen ancak `as_friend` niteleyicisi içinde ilk a geçişi değil kullanıldı; derleyici ikinci yoksayacak `as_friend`.  
  
 Daha fazla bilgi için bkz: [arkadaş derlemeler (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir bileşen oluşturur.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4364 oluşturur.  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```