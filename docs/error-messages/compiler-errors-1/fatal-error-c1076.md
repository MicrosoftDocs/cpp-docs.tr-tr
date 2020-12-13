---
description: 'Daha fazla bilgi edinin: önemli hata C1076'
title: Önemli hata C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: 2d2ca5ffc8970affa6ddd01011e1a37c7b5b778d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341808"
---
# <a name="fatal-error-c1076"></a>Önemli hata C1076

> derleyici sınırı: iç yığın sınırı aşıldı; daha yüksek bir sınır belirtmek için /Zm kullanın

Bu hata, çok fazla sembol veya çok fazla sayıda şablon örneklenmesi nedeniyle meydana gelir. Visual Studio 2015 ' den itibaren, bu ileti çok fazla paralel derleme işlemi nedeniyle Windows sanal belleği basıncına neden olabilir. Bu durumda, bir yönerge kullanmadığınız sürece **/ze** seçeneğinin kullanılması önerisi göz ardı edilmelidir `#pragma hdrstop` .

Bu hatayı gidermek için:

1. Ön derlenmiş üstbilgileriniz bir `#pragma hdrstop` yönerge kullanıyorsa, derleyici belleği sınırını [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) hata iletisinde belirtilen değere ayarlamak için [/zı](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneğini kullanın. Visual Studio 'da bu değerin nasıl ayarlanacağını içeren daha fazla bilgi için/ZD içindeki açıklamalar bölümüne bakın [(önceden derlenmiş üst bilgi bellek ayırma sınırını belirtin)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).

1. CL.EXE için **/MP** seçeneği ile birlikte MSBUILD.EXE için **/maxcpucount** seçeneğini kullanarak belirtilen paralel işlem sayısını azaltmayı göz önünde bulundurun. Daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi (pch) sorunları ve önerileri](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

1. 64-bit işletim sisteminde 32-bit barındırılan derleyiciler kullanıyorsanız, bunun yerine 64-bit barındırılan derleyiciler kullanın. Daha fazla bilgi için, bkz. [nasıl yapılır: 64 bit Visual C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. Gereksiz ekleme dosyalarını silin.

1. Gereksiz genel değişkenleri ortadan kaldırın (örneğin, büyük bir diziyi bildirmek yerine dinamik bellek ayırma).

1. Kullanılmayan bildirimleri ortadan kaldırın.

C1076, derleme başladıktan hemen sonra gerçekleşirse, **/ZD** için belirtilen değer, programınız için büyük olasılıkla çok yüksektir. **/ZD** değerini azaltın.
