---
title: Çağıran-Çağrılan Kaydedilmiş Yazmaçlar
ms.date: 11/04/2016
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
ms.openlocfilehash: f34fbfff8e6c61b5d568c073f6b7da2a12e34535
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654707"
---
# <a name="callercallee-saved-registers"></a>Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar

İşlev çağrılarında RAX'daki, RCX, RDX, R8, R9, R10, R11 geçici olarak kabul edilir ve dikkate alınması gereken kayıtları yok (sürece Aksi durumda güvenlik-kanıtlanabilir bütün program iyileştirmesi gibi analiz tarafından).

Yazmaçları RBX, RBP, RDI, RSI, RSP, R12, R13, R14 ve R15 kayıtları kalıcı olarak kabul edilir ve kaydedilmesi gerekir ve bir işlev tarafından geri, bunları kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)