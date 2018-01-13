---
title: __unaligned | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __unaligned_cpp
dev_langs: C++
helpviewer_keywords: __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da662cf9cbe17539381766d37255e63d958fb7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unaligned"></a>__unaligned
`__unaligned` değiştiricisiyle bir işaretçiyi bildirdiğinizde, derleyici işaretçinin hizalanmamış verilere yönelik olduğunu varsayar. Sonuç olarak derleyici, Itanium İşlemci Ailesi (IPF) bilgisayarını hedefleyen bir uygulama için hizalanmamış verileri bir kerede bir bayt olarak okuyan kod oluşturur.  
  
## <a name="remarks"></a>Açıklamalar  
 `__unaligned` Değiştiricisi için geçerli [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] ve [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] derleyicileri ancak IPF bilgisayarı hedef yalnızca uygulamaları etkiler. Bu değiştirici, yalnızca ele alınan verilerin hizalamasını açıklar; işaretçinin hizalandığı varsayılır.  
  
 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] İşlemci yanlış hizalanmış verilere erişen ve hata işleme süresi performans düzeyini düşürür hizalama hatası oluşturur. İşlemcinin verileri bir kerede bir bayt olarak okumasını sağlamak ve hatadan kaçınmak için `__unaligned` değiştiricisini kullanın. Bu değiştirici için gerekli değildir [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] uygulamaları çünkü [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] işlemci hatalı olmadan yanlış hizalanmış verilerini işler.  
  
 Hizalama hakkında daha fazla bilgi için bkz.  
  
-   [Hizalama](../cpp/align-cpp.md)  
  
-   [__alignof İşleci](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [/ZP (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Yapı Hizalama Örnekleri](../build/examples-of-structure-alignment.md)  
  
## <a name="example"></a>Örnek  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)