---
title: Önemli hata C1004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88f76c00c8f5b36acf238f0da88e908eac6dbe8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1004"></a>Önemli hata C1004
Beklenmeyen bulunan dosya sonu  
  
 Derleyici bir yapı çözümlemeden bir kaynak dosya sonuna ulaşıldı. Kod aşağıdaki öğelerden birini eksik olabilir:  
  
-   Bir kapanış ayracı  
  
-   Bir kapanış ayracı  
  
-   Kapatma açıklama işareti (* /)  
  
-   Noktalı virgül  
  
 Bu hatayı gidermek için aşağıdakileri denetleyin:  
  
-   Varsayılan disk sürücüsü kaynak dosyası olarak iki katı kadar alan hakkında gerekli geçici dosyalar için yeterli alan yok.  
  
-   Bir `#if` false oturumda kapatma değerlendirir yönergesi `#endif` yönergesi.  
  
-   Kaynak dosyaya bir satır başı ve satır besleme ile bitmez.  
  
 Aşağıdaki örnek C1004 oluşturur:  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 Olası çözüm:  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```