---
title: Önemli hata C1060 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5aa168c185bafbfd6fadf3f0d5f1320ba4f43d60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1060"></a>Önemli hata C1060
yığın alanı kalmadı derleyicisidir  
  
 İşletim sistemi veya çalışma zamanı kitaplığı bellek için bir istek doldurun olamaz.  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Bu hatayı gidermek için aşağıdaki olası çözümlere deneyin  
  
1.  Derleyici hataları yayımlıyorsa [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) ve [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), kullanın [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) bellek ayırma sınırını düşürmek için derleyici seçeneği. Daha fazla yığın alanı uygulamanıza kullanılabilir durumdaysa kalan bellek ayırma düşürün.  
  
     Varsa [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği zaten ayarlanmış, bu kaldırmayı deneyin. Seçeneğinde belirtilen bellek ayırma sınırını çok yüksek olduğundan yığın alanı tükendi. Derleyici kaldırdığınız varsayılan bir sınır kullanıyorsa [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği.  
  
2.  Bir 64-bit platformda derleme, 64 bit derleyici araç setini kullanın. Bilgi için bkz: [nasıl yapılır: bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirmek](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  32-bit Windows sürümlerinde kullanmayı deneyin [3 GB](http://go.microsoft.com/fwlink/p/?linkid=177831) boot.ini anahtarı.  
  
4.  Windows takas dosyası boyutunu artırın.  
  
5.  Diğer çalışan programları kapatın.  
  
6.  Gereksiz ekleme dosyalarını silin.  
  
7.  Örneğin, gereksiz genel değişkenler, uzun bir diziye bildirme yerine dinamik olarak bellek ayırarak ortadan kaldırır.  
  
8.  Kullanılmayan bildirimleri ortadan kaldırın.  
  
9. Geçerli dosyayı daha küçük dosyalara bölün.