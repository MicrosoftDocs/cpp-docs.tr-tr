---
title: Bağlayıcı Araçları Uyarısı LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: dc81df89609f59834c8a3271dd64f3b99b281f90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613648"
---
# <a name="linker-tools-warning-lnk4206"></a>Bağlayıcı Araçları Uyarısı LNK4206

> önceden derlenmiş tür bilgileri bulunamadı; '*filename*' değil bağlantılı veya üzerine yazılmış; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

*Filename* kullanarak derlenen nesne dosyası, [/Yc](../../build/reference/yc-create-precompiled-header-file.md), ya da bağlantı komutunda belirtilmedi veya yazıldı.

Bu uyarı için yaygın bir senaryo, /Yc ile derlenen .obj kitaplığa olduğunda ve bu .obj kodunuzdan hiçbir sembol başvuruları olduğu ' dir.  Bu durumda, bağlayıcı değil kullanmayı (veya hatta bakın) .obj dosyası.  Bu durumda, kodunuzu yeniden derleyin ve kullanmalısınız [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kullanılarak derlenmiş nesneleri için [/Yu](../../build/reference/yu-use-precompiled-header-file.md).