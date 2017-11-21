---
title: "Derleyici Uyarısı C4958 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4958
dev_langs: C++
helpviewer_keywords: C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 932f12c5465d08db22c7bac977dfeab94d61f1f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4958"></a>Derleyici Uyarısı C4958
'işlemi': işaretçi aritmetiği doğrulanabilen değil  
  
 İşaretçi aritmetiği kullanarak doğrulanamayan bir görüntü oluşturur.  
  
 Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Bu uyarıyı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.  
  
 Aşağıdaki örnek C4958 oluşturur:  
  
```  
// C4958.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
using namespace System;  
  
int main( ) {  
   Int32 arr[] = new Int32[10];  
   Int32* p = &arr[0];  
   p++;   // C4958  
}  
```  
  
 İşaretçi aritmetiği dizi işlemleriyle derleyici uygular. Bu nedenle, yerel diziler doğrulanabilir değildir; CLR dizisi kullanın. Daha fazla bilgi için bkz: [dizi](../../windows/arrays-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C4958 oluşturur:  
  
```  
// C4958b.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4958 )  
  
int main() {  
   int array[5];  
   array[4] = 0;   // C4958  
}  
```