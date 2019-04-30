---
title: Derleyici Hatası C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 9b20224207ba797c6ee93c06404e4d90c3d02525
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391887"
---
# <a name="compiler-error-c3859"></a>Derleyici Hatası C3859

> sanal bellek aralığı için PCH aştı; Lütfen bir komut satırı seçeneği ile yeniden derle '-Zm*değer*' veya üzeri

Sanal belleği, önceden derlenmiş üst bilgi için derleyicinin koymak çalışılırken veri miktarı çok küçüktür. Visual Studio 2015'ten başlayarak **/Zm** öneri yalnızca önemli kullanırken `#pragma hdrstop` yönergesi. Diğer durumlarda, Windows sanal bellek baskısı sorunları gösteren sahte bir hata var.

Önceden derlenmiş üst bilgi kullanıyorsa bir `#pragma hdrstop` yönergesi, kullanım **/Zm** önceden derlenmiş üstbilgi dosyası için daha büyük bir değer belirtmek için derleyici bayrağı. Aksi takdirde yapınız paralel derleme işlem sayısını azaltmayı deneyin. Daha fazla bilgi için [/Zm (belirtin önceden derlenmiş üst bilgi bellek ayırma sınırını)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
