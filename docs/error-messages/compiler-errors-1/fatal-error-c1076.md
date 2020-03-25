---
title: Önemli hata C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: ca5117342d406983e8cba675c2589d2431d09d38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204184"
---
# <a name="fatal-error-c1076"></a>Önemli hata C1076

> derleyici sınırı: iç yığın sınırı aşıldı; daha yüksek bir sınır belirtmek için /Zm kullanın

Bu hata, çok fazla sembol veya çok fazla sayıda şablon örneklenmesi nedeniyle meydana gelir. Visual Studio 2015 ' den itibaren, bu ileti çok fazla paralel derleme işlemi nedeniyle Windows sanal belleği basıncına neden olabilir. Bu durumda, bir `#pragma hdrstop` yönergesi kullanmadığınız sürece **/ze** seçeneğinin kullanılması önerisi göz ardı edilmelidir.

Bu hatayı gidermek için:

1. Önceden derlenmiş üstbilgileriniz bir `#pragma hdrstop` yönergesi kullanıyorsa, derleyici belleği sınırını [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) hata iletisinde belirtilen değere ayarlamak için [/zı](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneğini kullanın. Visual Studio 'da bu değerin nasıl ayarlanacağını içeren daha fazla bilgi için/ZD içindeki açıklamalar bölümüne bakın [(önceden derlenmiş üst bilgi bellek ayırma sınırını belirtin)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).

1. MSBUILD için **/maxcpucount** seçeneğini kullanarak belirtilen paralel işlem sayısını azaltmayı göz önünde bulundurun. Öğesini CL ile birlikte kullanarak **/MP** exe. EXE. Daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi (pch) sorunları ve önerileri](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

1. 64-bit işletim sisteminde 32-bit barındırılan derleyiciler kullanıyorsanız, bunun yerine 64-bit barındırılan derleyiciler kullanın. Daha fazla bilgi için, bkz. [nasıl yapılır: 64 bitlik görsel C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. Gereksiz ekleme dosyalarını silin.

1. Gereksiz genel değişkenleri ortadan kaldırın (örneğin, büyük bir diziyi bildirmek yerine dinamik bellek ayırma).

1. Kullanılmayan bildirimleri ortadan kaldırın.

C1076, derleme başladıktan hemen sonra gerçekleşirse, **/ZD** için belirtilen değer, programınız için büyük olasılıkla çok yüksektir. **/ZD** değerini azaltın.
