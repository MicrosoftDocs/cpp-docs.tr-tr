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
ms.openlocfilehash: 1c148803da11ea85857cb77753d2e6af6a6ae22e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="unaligned"></a>__unaligned
`__unaligned` değiştiricisiyle bir işaretçiyi bildirdiğinizde, derleyici işaretçinin hizalanmamış verilere yönelik olduğunu varsayar. Sonuç olarak derleyici, Itanium İşlemci Ailesi (IPF) bilgisayarını hedefleyen bir uygulama için hizalanmamış verileri bir kerede bir bayt olarak okuyan kod oluşturur.  
  
## <a name="remarks"></a>Açıklamalar  
 `__unaligned` Değiştiricisi için geçerli [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] ve [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] derleyicileri ancak IPF bilgisayarı hedef yalnızca uygulamaları etkiler. Bu değiştirici, yalnızca ele alınan verilerin hizalamasını açıklar; işaretçinin hizalandığı varsayılır.  
  
 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] İşlemci yanlış hizalanmış verilere erişen ve hata işleme süresi performans düzeyini düşürür hizalama hatası oluşturur. İşlemcinin verileri bir kerede bir bayt olarak okumasını sağlamak ve hatadan kaçınmak için `__unaligned` değiştiricisini kullanın. Bu değiştirici için gerekli değildir [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] uygulamaları çünkü [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] işlemci hatalı olmadan yanlış hizalanmış verilerini işler.  
  
 Hizalama hakkında daha fazla bilgi için bkz.  
  
-   [Hizalama](../cpp/align-cpp.md)  
  
-   [__alignof işleci](../cpp/alignof-operator.md)  
  
-   [Paketi](../preprocessor/pack.md)  
  
-   [/ZP (yapı üyesi hizalama)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Yapı hizalama örnekleri](../build/examples-of-structure-alignment.md)  
  
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
 [Anahtar sözcükler](../cpp/keywords-cpp.md)