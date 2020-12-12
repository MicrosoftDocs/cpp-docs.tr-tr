---
description: Şu konuda daha fazla bilgi edinin:/INTEGRITYCHECK
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b1ea8275bdb356febcf18a2a55b6ab718d8eea96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199668"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

İkili görüntünün dijital imzasının yükleme zamanında denetlenmesi gerektiğini belirtir.

> **/IntegrityCheck**[**: No**]

## <a name="remarks"></a>Açıklamalar

DLL dosyasının veya yürütülebilir dosyanın üstbilgisinde, bu seçenek, görüntüyü Windows 'a yüklemek için bellek Yöneticisi tarafından dijital imza denetimi gerektiren bir bayrak ayarlar. Windows Vista 'dan önceki Windows sürümleri bu bayrağı yoksayar. Bu seçenek, çekirdek modu kodu uygulayan 64-bit DLL 'Ler için ayarlanmalıdır ve tüm cihaz sürücüleri için önerilir. Daha fazla bilgi için bkz. [çekirdek modu kod Imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
