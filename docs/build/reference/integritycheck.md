---
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: 4174e22dcdadb3b3319998614285c13741fe3a88
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814258"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

İkili görüntünün dijital imzasının yükleme sırasında denetlenmesi gerektiğini belirtir.

> **/ INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>Açıklamalar

DLL dosyasının veya yürütülebilir dosya üst bilgisinde, bu seçenek Windows görüntüyü yüklemek için bellek yöneticisi tarafından bir dijital imza denetimi gerektiren bir bayrak ayarlar. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yoksayın. Bu seçenek, çekirdek modu kodunu uygulayan ve tüm cihaz sürücüleri için tavsiye edilir 64-bit DLL'ler için ayarlanması gerekir. Daha fazla bilgi için [çekirdek modu kod imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
