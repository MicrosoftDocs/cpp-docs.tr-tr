---
description: 'Daha fazla bilgi edinin: önemli hata C1510'
title: Önemli hata C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: 3112874f033fdeed4cc4290b2469105a275baed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276328"
---
# <a name="fatal-error-c1510"></a>Önemli hata C1510

Dil kaynağı açılamıyor clui.dll

Derleyici, dil kaynağı DLL 'sini yükleyemiyor.

Bu sorunun iki yaygın nedeni vardır. 32 bit derleyicisini ve araçları kullanırken, bir bağlantı sırasında 2 GB 'den fazla bellek kullanan büyük projeler için bu hatayı görebilirsiniz. 64 bitlik Windows sistemlerine yönelik olası bir çözüm, kodunuzu oluşturmak için 64 bit yerel veya çapraz derleyicisini ve araçları kullanmaktır. Bu, 64 bitlik uygulamalarda kullanılabilen daha büyük bellek alanından yararlanır. 32 bit sistemde çalıştırdığınız için 32 bitlik bir derleyici kullanmanız gerekiyorsa, bazı durumlarda bağlayıcı için kullanılabilir bellek miktarını 3GB olarak artırabilirsiniz. Daha fazla bilgi için bkz. [4 gigabayt ayarlama: bcdedit ve Boot.ini](/windows/win32/memory/4-gigabyte-tuning) ve [bcdedit/set ınseuserva](/windows-hardware/drivers/devtest/bcdedit--set) komutu.

Diğer yaygın neden, bozuk veya tamamlanmamış bir Visual Studio yüklemesidir. Bu durumda, Visual Studio 'Yu onarmak veya yeniden yüklemek için yükleyiciyi yeniden çalıştırın.
