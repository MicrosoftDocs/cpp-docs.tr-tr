---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3859'
title: Derleyici hatası C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 25c05425072cda6924d90f08c9aeff7446a4e85b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336106"
---
# <a name="compiler-error-c3859"></a>Derleyici hatası C3859

> PCH için sanal bellek aralığı aşıldı; Lütfen '-ZM *Value*' veya daha büyük bir komut satırı seçeneğiyle yeniden derleyin

Ön derlenmiş üst bilgi için ayrılan sanal bellek, derleyicinin kendisine koymaya çalıştığı veri miktarı için çok küçük. Visual Studio 2015 ' den başlayarak **/za** önerisi yalnızca yönerge kullanılırken önemlidir `#pragma hdrstop` . Diğer durumlarda, Windows sanal bellek baskısı sorunlarını gösteren bir çok değerli hatadır.

Ön derlenmiş üst bilgi bir `#pragma hdrstop` yönerge kullanıyorsa, önceden derlenmiş üstbilgi dosyası için daha büyük bir değer belirtmek üzere **/zı** derleyici bayrağını kullanın. Aksi takdirde, derinizdeki paralel derleme işlemlerinin sayısını azaltmayı göz önünde bulundurun. Daha fazla bilgi için bkz. [/ZD (önceden derlenmiş üst bilgi bellek ayırma sınırını belirt)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).
