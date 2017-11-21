---
title: "Derleyici Uyarısı (düzey 1) C4532 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4532
dev_langs: C++
helpviewer_keywords: C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5cec2f70dfa6781c237cc1c08079904c7b48e171
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4532"></a>Derleyici Uyarısı (düzey 1) C4532
'Devam': atlama __finally/finally bloğu dışında davranış sonlandırma işleme sırasında tanımlanmamış  
  
 Derleyici şu anahtar sözcüklerden biri karşılaştı:  
  
-   [devam etmek](../../cpp/continue-statement-cpp.md)  
  
-   [sonu](../../cpp/break-statement-cpp.md)  
  
-   [Git](../../cpp/goto-statement-cpp.md)  
  
 dışında bir atlama neden bir [__finally](../../cpp/try-finally-statement.md) veya [son](../../dotnet/finally.md) anormal sonlandırma sırasında bloğu.  
  
 Bir özel durum oluşursa ve yığın sonlandırma işleyicileri yürütülmesi sırasında sapmasına sırada ( `__finally` veya finally blokları), ve işyeri dışında kodunuzu atlar bir `__finally` önce engelle `__finally` davranışı blok sona erdiğinde tanımlanmadı. Özel durum düzgün işlenmemiş şekilde denetim unwinding kodu döndürmeyebilir.  
  
 İşyeri dışında atlamanız gerekir, bir **__finally** engellemek, anormal sonlandırma için önce kontrol edin.  
  
 Aşağıdaki örnek C4532 oluşturur; Yalnızca açıklama uyarıları çözümlemek için atlama deyimleri çıkışı.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```