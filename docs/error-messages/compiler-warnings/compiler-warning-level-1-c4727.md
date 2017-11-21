---
title: "Derleyici Uyarısı (düzey 1) C4727 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4727
dev_langs: C++
helpviewer_keywords: C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15a8a74fc4c15e507fc8a651e9849fc82e3b9c38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4727"></a>Derleyici Uyarısı (düzey 1) C4727
"Obj_file_1 ve obj_file_2 bulunan aynı zaman damgasına sahip pch_file adlı PCH.  İlk PCH kullanma.  
  
 C4727 oluşur ile birden çok derleme derlerken **/Yc**, ve derleyici bulunduğu aynı .pch zaman damgasına sahip tüm .obj dosyaları kullanabilirsiniz.  
  
 Çözmek için bir kaynak dosyayla derleme **/Yc /c** (pch oluşturur) ve diğerleri ile ayrı olarak derleme **/Yu /c** (pch kullanır), bunları birbirine bağlayabilirsiniz.  
  
 Bunu, aşağıdaki vermedi ve C4727 oluşturur:  
  
 **cl/CLR /GL a.cpp b.cpp c.cpp /Ycstdafx.h**  
  
 Bunun yerine aşağıdakileri:  
  
 **cl/CLR /GL a.cpp /Ycstdafx.h /c**  
  
 **cl/CLR /GL b.cpp c.cpp /Yustdafx.h/Link a.obj**  
  
 Daha fazla bilgi için bkz.  
  
-   [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (önceden derlenmiş başlık dosyasını)](../../build/reference/yu-use-precompiled-header-file.md)