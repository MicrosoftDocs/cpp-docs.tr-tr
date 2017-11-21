---
title: "Derleyici Hatası C3461 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3461
dev_langs: C++
helpviewer_keywords: C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27cc201ff7b11b5a44179d5a678bee42d0b21609
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3461"></a>Derleyici Hatası C3461
'type': yalnızca bir yönetilen türü iletilebilir  
  
 Tür iletme yalnızca CLR türleri üzerinde oluşabilir.  Bkz: [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md) daha fazla bilgi için.  
  
 Daha fazla bilgi için bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir bileşen oluşturur.  
  
```  
// C3461.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3461 oluşturur.  
  
```  
// C3461b.cpp  
// compile with: /clr /c  
#using "C3461.dll"  
class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3461  
[assembly:TypeForwardedTo(R::typeid)];   // OK  
```