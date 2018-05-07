---
title: Derleyici Uyarısı (düzey 1) C4727 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c92e42fe275f821e333a0f04a116034a5bb849a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
  
-   [/Yc (Önceden Derlenmiş Üst Bilgi Dosyası Oluştur)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (Önceden Derlenmiş Üst Bilgi Dosyasını Kullanma)](../../build/reference/yu-use-precompiled-header-file.md)