---
title: "Derleyici Hatası C3383 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3383
dev_langs:
- C++
helpviewer_keywords:
- C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4edf434b9bd1d7a1e8c6609541bd29fab3c0e66d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3383"></a>Derleyici Hatası C3383
/ CLR: safe ile 'Yeni ' işleci desteklenmiyor  
  
 Çıktı dosyası bir **/CLR: safe** derleme doğrulanabilir şekilde güvenli türü olan bir dosya olduğundan ve işaretçiler desteklenmez.  
  
 Daha fazla bilgi için bkz:  
  
-   [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3383 oluşturur.  
  
```  
// C3383.cpp  
// compile with: /clr:safe  
int main() {  
   char* pCharArray = new char[256];  // C3383  
}  
```