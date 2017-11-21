---
title: "Derleyici Hatası C2261 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2261
dev_langs: C++
helpviewer_keywords: C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8269b891ed899501625973b81c1823d4db2d56c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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