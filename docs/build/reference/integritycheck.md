---
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b3f6622e3628db53c363b239c59accd94f708ab0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617284"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

İkili görüntünün dijital imzasının yükleme sırasında denetlenmesi gerektiğini belirtir.

> **/ INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>Açıklamalar

DLL dosyasının veya yürütülebilir dosya üst bilgisinde, bu seçenek Windows görüntüyü yüklemek için bellek yöneticisi tarafından bir dijital imza denetimi gerektiren bir bayrak ayarlar. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yoksayın. Bu seçenek, çekirdek modu kodunu uygulayan ve tüm cihaz sürücüleri için tavsiye edilir 64-bit DLL'ler için ayarlanması gerekir. Daha fazla bilgi için [çekirdek modu kod imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)
