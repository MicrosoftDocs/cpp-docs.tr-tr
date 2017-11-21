---
title: "Derleyici Hatası C3069 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3069
dev_langs: C++
helpviewer_keywords: C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6470ec9177ee1478c691fa3afb2c5e997e16be8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3069"></a>Derleyici Hatası C3069
'işleci': numaralandırma türü için izin verilmiyor  
  
 CLR Numaralandırma için bir işleç desteklenmiyor.  Daha fazla bilgi için bkz: [nasıl yapılır: C + numaralandırmaları tanımlama ve kullanma +/ CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3069 oluşturur:  
  
```  
// C3069.cpp  
// compile with: /clr  
enum struct E { e1 };  
enum F { f1 };  
  
int main() {  
   E e = E::e1;  
   bool tf;  
   tf = !e;   // C3069  
  
   // supported for native enums  
   F f = f1;  
   tf = !f;  
}  
```