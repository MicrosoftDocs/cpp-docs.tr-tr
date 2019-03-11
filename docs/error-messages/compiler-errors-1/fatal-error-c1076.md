---
title: Önemli hata C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: 91753a49498548b4e523cd8564ee7a7ca7a3b373
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751680"
---
# <a name="fatal-error-c1076"></a>Önemli hata C1076

> derleyici sınırı: iç yığın sınırı aşıldı; daha yüksek bir sınır belirtmek için /Zm kullanın

Bu hata, çok fazla sembol veya çok fazla sayıda şablon örneklenmesi nedeniyle meydana gelir. Visual Studio 2015'ten başlayarak, bu ileti gelen çok fazla paralel derleme işlemler tarafından neden Windows sanal bellek baskısı neden olabilir. Bu durumda, kullanılacak öneri **/Zm** seçeneği yoksayılan kullanmakta olduğunuz sürece bir `#pragma hdrstop` yönergesi.

Bu hatayı gidermek için:

1. Önceden derlenmiş üst bilgi kullanıyorsa bir `#pragma hdrstop` yönergesi, kullanım [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) derleyici bellek sınırını belirtilen değere ayarlamak için seçeneği [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) hata iletisi. Visual Studio'da bu değeri ayarlamak nasıl içeren daha fazla bilgi için bkz açıklamalar bölümünde [/Zm (belirtin önceden derlenmiş üst bilgi bellek ayırma sınırını)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).

1. Kullanılarak belirtilen paralel işlem sayısını azaltmayı deneyin **/maxcpucount** MSBUILD seçeneği. EXE birlikte **/MP** CL seçeneği. EXE. Daha fazla bilgi için [önceden derlenmiş üst bilgi (PCH) sorunları ve önerilerini](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

1. 64-bit işletim sisteminde 32-bit barındırılan derleyiciler kullanıyorsanız, bunun yerine 64-bit barındırılan derleyiciler kullanın. Daha fazla bilgi için [nasıl yapılır: Bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. Gereksiz ekleme dosyalarını silin.

1. Gereksiz genel değişkenleri ortadan kaldırın (örneğin, büyük bir diziyi bildirmek yerine dinamik bellek ayırma).

1. Kullanılmayan bildirimleri ortadan kaldırın.

İçin belirtilen değer derleme başladıktan hemen C1076 oluşursa **/Zm** muhtemelen programınız için çok yüksektir. Azaltma **/Zm** değeri.