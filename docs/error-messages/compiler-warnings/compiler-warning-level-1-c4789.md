---
title: Derleyici Uyarısı (düzey 1) C4789 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4789
dev_langs:
- C++
helpviewer_keywords:
- C4789
ms.assetid: 5800c301-5afb-4af0-85c1-ceb54d775234
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8b16fada030783f5f9e3aa3d1f9a04e7743a13c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282993"
---
# <a name="compiler-warning-level-1-c4789"></a>Derleyici Uyarısı (düzey 1) C4789
Arabellek boyutu N bayt ' tanıtıcısı' taşması; M bayt L uzaklıkta başlayan yazılır.  
  
 Sizi uyarır belirli C çalışma zamanı (CRT) işlevlerini kullanıldığında, taşması hakkında parametreler iletilir ve atamaları gerçekleştirilir, sağlayacak şekilde veri boyutları derleme zamanında bilinir. Bu uyarı, normal veri boyutu uyuşmazlığı algılama elude durumlar için değil.  
  
 Veri uzunluğunu en bilinen, derleme zamanı, kopyalanır ve büyüklüğü derleme zamanında veri için çok küçük bilinen bir veri bloğunun yerleştirin olduğunda bir uyarı görüntülenir. Aşağıdaki CRT işlevleri birinin iç formunu kullanarak kopyalama yapılması gerekir:  
  
-   [strcpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)  
  
-   [memset](../../c-runtime-library/reference/memset-wmemset.md)  
  
-   [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md), [wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)  
  
 Uyarı ayrıca bir cast kullanarak bir parametre veri türü eşleşmiyor ve ardından bir lvalue başvuru kopyalama ağından denenir görüntülenir.  
  
 Visual C++ olmayan herhangi bir zamanda çalıştırma bir kod yolu için bu uyarı oluşturabilir. Kullanarak geçici olarak uyarı devre dışı bırakabilirsiniz `#pragma`, bu örnekte gösterildiği gibi:  
  
 `#pragma(push)`  
  
 `#pragma warning ( disable : 4789 )`  
  
 `// unused code that generates compiler warning C4789`  
  
 `#pragma(pop)`  
  
 Bu, Visual C++ belirli bloğu kod için uyarı üretme tutar. `#pragma(push)` Önce mevcut durumu korur `#pragma warning(disable: 4789)` değiştirir. `#pragma(pop)` Basılmış durumunu geri yükler ve etkilerini kaldırır `#pragma warning(disable:4789)`. C++ önişlemci yönergesi hakkında daha fazla bilgi için `#pragma`, bkz: [uyarı](../../preprocessor/warning.md) ve [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4789 oluşturur.  
  
```  
// C4789.cpp  
// compile with: /Oi /W1 /c  
#include <string.h>  
#include <stdio.h>  
  
int main()   
{  
    char a[20];  
    strcpy(a, "0000000000000000000000000\n");   // C4789  
  
    char buf2[20];  
    memset(buf2, 'a', 21);   // C4789  
  
    char c;  
    wchar_t w = 0;  
    memcpy(&c, &w, sizeof(wchar_t));  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ayrıca C4789 oluşturur.  
  
```  
// C4789b.cpp  
// compile with: /W1 /O2 /c  
// processor: x86  
short G;  
  
void main()  
{  
   int * p = (int *)&G;   
   *p = 3;   // C4789 - writes an int through a pointer to short  
}   
```