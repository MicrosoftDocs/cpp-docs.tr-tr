---
title: "Derleyici Uyarısı (Düzey 2 ve 4) C4200 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4200
dev_langs: C++
helpviewer_keywords: C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f160476deb2ab3e4ad0ff00100305c934dfb14c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Derleyici Uyarısı (Düzey 2 ve 4) C4200
kullanılan standart olmayan uzantısı: sıfır boyutlu dizi struct/Birleşimdeki  
  
 Bir yapının veya birleşimin sıfır boyutuna sahip bir dizi içerdiğini gösterir.  
  
 Bir Microsoft uzantısı bildirimidir sıfır boyutlu dizi. Bir C dosyası derlendiğinde bu C++ dosyasına derlendiğinde bir düzey 2 uyarı ve düzey 4 uyarı neden olur. C++ derleme ayrıca bu uyarı verir: "UDT sıfır boyutlu bir array içerdiğinde copy ctor veya kopya atama işleci oluşturamıyor." Bu örnek uyarı C4200 oluşturur:  
  
```cpp  
// C4200.cpp  
// compile by using: cl /W4 c4200.cpp  
struct A {  
    int a[0];  // C4200  
};  
int main() {  
}  
```  
  
 Bu standart uzantısı genellikle değişken uzunlukta olan dış veri yapılarını arabirimi koduyla için kullanılır. Bu senaryo için kodunuzu geçerliyse, uyarıyı devre dışı bırakabilirsiniz:  
  
## <a name="example"></a>Örnek  
  
```cpp  
// C4200b.cpp  
// compile by using: cl /W4 c4200a.cpp  
#pragma warning(disable : 4200)  
struct A {  
    int a[0];  
};  
int main() {  
}  
```