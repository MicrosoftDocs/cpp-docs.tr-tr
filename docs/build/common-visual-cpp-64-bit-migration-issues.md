---
title: "Genel Visual C++ 64-bit geçiş sorunları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- upgrading Visual C++ applications, 32-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 957ac623aff18dbcb2d7f3418cc5acc96085c154
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Genel Visual C++ 64 Bit Geçiş Sorunları

Bir 64-bit Windows işletim sisteminde çalışacak uygulamaları oluşturmak için Visual C++ kullandığınızda aşağıdaki konuları göz bilmeniz gerekir:  
  
-   Bir `int` ve `long` 64-bit Windows işletim sistemlerinde 32-bit değerlerdir. 64 bit platformları derlemek için plan programları işaretçileri 32-bit değişkenlere atamamaya olması gerekir. İşaretçiler bir 32 bit değişken atarsanız, 64-bit ve 64 bit platformları işaretçi değeri kesmek.  
  
-   `size_t`, `time_t`, ve `ptrdiff_t` 64-bit Windows işletim sistemlerinde 64-bit değerlerdir.  
  
-   `time_t`bir 32 bit 32-bit Windows işletim sistemlerinde Visual C++ sürümlerinde Visual C++ 2005 önce değerdir. `time_t`bir 64-bit tamsayı varsayılan olarak sunulmuştur. Daha fazla bilgi için bkz: [zaman Yönetimi](../c-runtime-library/time-management.md).  
  
     Kodunuzu nereye aldığını ve bilmeniz gereken bir `int` değer ve olarak işleyen bir `size_t` veya `time_t` değeri. Sayı 32 bit sayıdan büyük olacak şekilde büyümesine ve veri geri geçirildiğinde kesilir mümkündür `int` depolama.  
  
%X (onaltılık `int` biçimi) `printf` değiştiricisi 64-bit Windows işletim sisteminde beklendiği gibi çalışmaz. Yalnızca ilk 32 bit kendisine geçirilen değerin üzerinde çalışır.  
  
-   Bir 32 bit tam sayı türü onaltılık biçimde görüntülemek için % I32x'i kullanın.  
  
-   % I64x bir 64-bit tam sayı türü onaltılık biçimde görüntülemek için kullanın.  
  
-   %P (onaltılık biçimde bir işaretçisi), bir 64-bit Windows işletim sisteminde beklendiği gibi çalışmaz.  
  
Daha fazla bilgi için bkz.:  
  
-   [Derleyici Seçenekleri](../build/reference/compiler-options.md)  
  
-   [Geçiş ipuçları](http://msdn.microsoft.com/library/windows/desktop/aa384214)  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ 64-bit, x64 için yapılandırma hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md)   
[Visual C++ taşıma ve yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)