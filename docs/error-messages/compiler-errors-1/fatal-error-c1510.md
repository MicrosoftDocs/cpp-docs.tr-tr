---
title: Önemli hata C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: 33c17a3099f4aed99cc26579d0e65c4a350b4268
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501089"
---
# <a name="fatal-error-c1510"></a>Önemli hata C1510

Clui. dll dil kaynağı açılamıyor

Derleyici, dil kaynağı DLL 'sini yükleyemiyor.

Bu sorunun iki yaygın nedeni vardır. 32 bit derleyicisini ve araçları kullanırken, bir bağlantı sırasında 2 GB 'den fazla bellek kullanan büyük projeler için bu hatayı görebilirsiniz. 64 bitlik Windows sistemlerine yönelik olası bir çözüm, kodunuzu oluşturmak için 64 bit yerel veya çapraz derleyicisini ve araçları kullanmaktır. Bu, 64 bitlik uygulamalarda kullanılabilen daha büyük bellek alanından yararlanır. 32 bit sistemde çalıştırdığınız için 32 bitlik bir derleyici kullanmanız gerekiyorsa, bazı durumlarda bağlayıcı için kullanılabilir bellek miktarını 3GB olarak artırabilirsiniz. Daha fazla bilgi için bkz [. 4 gigabayt ayarlama: Bcdedit ve Boot. ini](/windows/win32/memory/4-gigabyte-tuning) ve [bcdedit/set ınseuserva](/windows-hardware/drivers/devtest/bcdedit--set) komutu.

Diğer yaygın neden, bozuk veya tamamlanmamış bir Visual Studio yüklemesidir. Bu durumda, Visual Studio 'Yu onarmak veya yeniden yüklemek için yükleyiciyi yeniden çalıştırın.
