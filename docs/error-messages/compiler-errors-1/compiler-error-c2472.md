---
title: "Derleyici Hatası C2472 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2472
dev_langs: C++
helpviewer_keywords: C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed41a3d78ab9652d1e88ceefe29011eb5b2225a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2472"></a>Derleyici Hatası C2472
Yönetilen kodda 'function' oluşturulamıyor: 'iletisi'; karma bir görüntü oluşturmak için/CLR ile derleme  
  
 Yönetilen kod tarafından desteklenmeyen türleri içinde saf ortak dil çalışma zamanı (CLR) ortamı kullanıldığında bu hata meydana gelir. İle derleme **/CLR** hatayı gidermek için.  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2472 oluşturur.  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)