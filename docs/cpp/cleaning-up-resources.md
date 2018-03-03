---
title: "Kaynakları temizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd84fdd041a3b3715c4fbfa9b4c1d78fdf2ba464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-resources"></a>Kaynakları Temizleme
Sonlandırma işleyicisi yürütülürken, sonlandırma işleyicisi çağrılmadan önce hangi kaynakların gerçekten ayrıldığını bilemeyebilirsiniz. Tüm kaynaklar ayrılmadan önce `__try` deyim bloğunun durdurulması olasıdır, böylece tüm kaynaklar açılmaz.  
  
 Bu nedenle, güvende olmak için, sonlandırma işleme temizleme işlemine devam etmeden önce hangi kaynakların açık olduğunu görmek için denetlemelisiniz. Önerilen bir yordam şöyledir:  
  
1.  Tanıtıcıları NULL olarak başlatın.  
  
2.  `__try` deyim bloğunda kaynakları ayırın. Kaynak ayırma işlemi yapılırken tanıtıcılar pozitif değerlere ayarlanır.  
  
3.  `__finally` deyim bloğunda, karşılık gelen tanıtıcısı veya bayrak değişkeni sıfır olmayan veya NULL olmayan her kaynağı serbest bırakın.  
  
## <a name="example"></a>Örnek  
 Örneğin, aşağıdaki kod, `__try` deyim bloğunda ayrılmış üç dosyayı ve bir bellek bloğunu kapatmak için bir sonlandırma işleyicisi kullanır. Kod, bir kaynağı silmeden önce kaynağın ayrılıp ayrılmadığını kontrol eder.  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)