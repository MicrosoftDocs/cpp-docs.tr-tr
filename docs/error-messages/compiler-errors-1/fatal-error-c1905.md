---
title: Önemli hata C1905
ms.date: 11/04/2016
f1_keywords:
- C1905
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
ms.openlocfilehash: 3fb4db30d91e0dd8c9dbeeebca46210122e5ff07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663164"
---
# <a name="fatal-error-c1905"></a>Önemli hata C1905

Ön uç ve arka uç uyumlu değil (aynı işlemci hedeflenmelidir)

Bir .obj dosyası, bir derleyici ön ucu (C1.dll) bu hedefleri bir işlemci x86 gibi ARM veya x64 tarafından oluşturulur, ancak farklı bir işlemciyi hedefliyor bir arka uç tarafından (C2.dll) okuyun, bu hata oluşur.

Bu sorunu düzeltmek için eşleşen bir ön uç ve arka uç kullandığınızdan emin olun. Visual Studio'da oluşturulan projeleri için varsayılan değer budur. Bu hata, proje dosyası düzenleme ve derleme araçları için farklı yollar kullanılan ortaya çıkabilir. Derleyici araçları yolunu özellikle ayarlamadıysanız, Visual Studio yüklemenizin bozuk olduğunda bu hata oluşabilir. Örneğin, derleyici .dll dosyaları bir konumdan diğerine kopyaladığınız. Kullanım **programlar ve Özellikler** Visual Studio'yu yeniden yükleyin veya onarmak için Windows Denetim Masası'nda.