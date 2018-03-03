---
title: "Derleyici Hatası C2261 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3907a1d270de11af82462815ce87398e10c50513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2261"></a>Derleyici Hatası C2261
'string': derleme başvurusu geçerli değil ve çözümlenemedi  
  
 Bir değeri geçerli değil.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>bir derlemeyi belirtmek için kullanılır. Örneğin, a.dll b.dll arkadaş derleme olarak belirtmek isterse, (a.dll içinde) belirtmeniz gerekir: InternalsVisibleTo("b"). Çalışma zamanı sonra her şeyi a.dll (dışında özel türleri) erişmek b.dll sağlar.  
  
 Arkadaş derlemeleri belirtirken doğru sözdizimi hakkında daha fazla bilgi için bkz: [arkadaş derlemeler (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2261 oluşturur.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```