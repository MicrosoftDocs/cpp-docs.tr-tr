---
title: Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8e877387dbb5b0be865e11017a3ac71a0c38faa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707661"
---
# <a name="callercallee-saved-registers"></a>Çağıran ve Çağrılan Kaydedilmiş Yazmaçlar

İşlev çağrılarında RAX'daki, RCX, RDX, R8, R9, R10, R11 geçici olarak kabul edilir ve dikkate alınması gereken kayıtları yok (sürece Aksi durumda güvenlik-kanıtlanabilir bütün program iyileştirmesi gibi analiz tarafından).

Yazmaçları RBX, RBP, RDI, RSI, RSP, R12, R13, R14 ve R15 kayıtları kalıcı olarak kabul edilir ve kaydedilmesi gerekir ve bir işlev tarafından geri, bunları kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)