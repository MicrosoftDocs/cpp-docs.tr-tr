---
title: Genel Visual C++ 64 bit geçiş sorunları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fadc3d48eb6ba812415cbedc9c077e7ffc1b4016
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208164"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Genel Visual C++ 64 Bit Geçiş Sorunları

Bir 64 bit Windows işletim sisteminde çalıştırılacak uygulamalar oluşturmak için Visual C++ kullandığınızda, aşağıdaki sorunlarından haberdar olmalı:  
  
-   Bir `int` ve `long` 64 bit Windows işletim sistemlerinde 32-bit değerleri. 64 bit platformları için derlemek için plan programları için işaretçiler, 32-bit değişkenlere atamamayı dikkatli olmanız gerekir. İşaretçiler bir 32-bit değişkene atarsanız, 64-bit ve 64-bit platformlarda işaretçi değeri truncate.  
  
-   `size_t`, `time_t`, ve `ptrdiff_t` 64 bit Windows işletim sistemlerinde 64 bitlik değerler.  
  
-   `time_t` bir 32-bit Visual C++ 2005 öncesi Visual C++ sürümlerinde 32 bit Windows işletim sistemlerinde değerdir. `time_t` Varsayılan olarak, 64 bitlik bir tamsayı olarak sunulmuştur. Daha fazla bilgi için [zaman Yönetimi](../c-runtime-library/time-management.md).  
  
     Kodunuzu nereye aldığını ve bilmeniz gereken bir `int` olarak işler ve değeri bir `size_t` veya `time_t` değeri. Sayı 32 bit bir sayı büyük olacak şekilde büyüyebilir ve verileri geri iletildiğinde kesilir mümkündür `int` depolama.  
  
%X (onaltılık `int` biçimi) `printf` değiştiricisi, bir 64 bit Windows işletim sisteminde beklendiği gibi çalışmaz. Yalnızca ilk 32 biti kendisine geçirilen değerin üzerinde çalışır.  
  
-   Onaltılık biçiminde bir 32 bit tamsayı türünü görüntülemek için % I32x'i kullanın.  
  
-   % I64x onaltılık biçiminde bir 64 bit tamsayı türünü görüntülemek için kullanın.  
  
-   %P (onaltılık biçimde bir işaretçi için), bir 64 bit Windows işletim sisteminde beklendiği gibi çalışır.  
  
Daha fazla bilgi için bkz.:  
  
-   [Derleyici Seçenekleri](../build/reference/compiler-options.md)  
  
-   [Geçiş ipuçları](/windows/desktop/WinProg64/migration-tips)  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ 64 bit x64 için yapılandırma hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md)   
[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)