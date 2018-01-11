---
title: "Önemli hata C1004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1004
dev_langs: C++
helpviewer_keywords: C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 528147eceadd35cc0d9fe656bdc7ce7965339a0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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