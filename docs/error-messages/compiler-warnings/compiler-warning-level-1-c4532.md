---
title: Derleyici Uyarısı (düzey 1) C4532 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4532
dev_langs:
- C++
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e37d36f565cc63c7cef9954a78e14ed60d676996
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285866"
---
# <a name="compiler-warning-level-1-c4532"></a>Derleyici Uyarısı (düzey 1) C4532
'Devam': atlama __finally/finally bloğu dışında davranış sonlandırma işleme sırasında tanımlanmamış  
  
 Derleyici şu anahtar sözcüklerden biri karşılaştı:  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
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