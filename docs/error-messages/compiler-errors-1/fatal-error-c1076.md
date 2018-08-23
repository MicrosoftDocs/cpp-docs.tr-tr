---
title: Önemli hata C1076 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1076
dev_langs:
- C++
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c02cc55280202b9ce576dc1e771b3428837209c8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465557"
---
# <a name="fatal-error-c1076"></a>Önemli hata C1076
derleyici sınırı: iç yığın sınırı aşıldı; daha yüksek bir sınır belirtmek için /Zm kullanın  
  
 Bu hata, çok fazla sembol veya çok fazla sayıda şablon örneklenmesi nedeniyle meydana gelir.  
  
 Bu hatayı gidermek için:  
  
1.  Kullanım [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) derleyici bellek sınırını belirtilen değere ayarlamak için seçeneği [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) hata iletisi. Visual Studio'da bu değeri ayarlamak nasıl içeren daha fazla bilgi için bkz açıklamalar bölümünde [/Zm (belirtin önceden derlenmiş üst bilgi bellek ayırma sınırını)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).  
  
2.  64-bit işletim sisteminde 32-bit barındırılan derleyiciler kullanıyorsanız, bunun yerine 64-bit barındırılan derleyiciler kullanın. Daha fazla bilgi için [nasıl yapılır: bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  Gereksiz ekleme dosyalarını silin.  
  
4.  Gereksiz genel değişkenleri ortadan kaldırın (örneğin, büyük bir diziyi bildirmek yerine dinamik bellek ayırma).  
  
5.  Kullanılmayan bildirimleri ortadan kaldırın.  
  
6.  Büyük işlevleri daha küçük işlevlere bölün.  
  
7.  Büyük sınıfları daha küçük sınıflara bölün.  
  
8.  Geçerli dosyayı daha küçük dosyalara bölün.  
  
 İçin belirtilen değer derleme başladıktan hemen C1076 oluşursa **/Zm** muhtemelen programınız için çok yüksektir. Azaltma **/Zm** değeri.