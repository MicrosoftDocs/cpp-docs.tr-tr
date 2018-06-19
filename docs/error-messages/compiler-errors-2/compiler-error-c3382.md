---
title: Derleyici Hatası C3382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3382
dev_langs:
- C++
helpviewer_keywords:
- C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8bcca58aecc3d5a5e7b621f45e102690c9f138c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254543"
---
# <a name="compiler-error-c3382"></a>Derleyici Hatası C3382
/ CLR: safe ile 'sizeof' desteklenmiyor  
  
 Çıktı dosyası bir **/CLR: safe** derleme doğrulanabilir şekilde güvenli türü olan bir dosya olduğundan ve sizeof büyüklüğü işletim sistemine bağlı olarak değişir size_t sizeof işleci dönüş değeri olduğu için desteklenmiyor.  
  
 Daha fazla bilgi için bkz:  
  
-   [sizeof İşleci](../../cpp/sizeof-operator.md)  
  
-   [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Genel Visual C++ 64 Bit Geçiş Sorunları](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3382 oluşturur.  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```