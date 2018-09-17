---
title: / INTEGRITYCHECK | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /INTEGRITYCHECK
dev_langs:
- C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 062ce019fe1b622661be880d8a06eac9c5971103
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709209"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

İkili görüntünün dijital imzasının yükleme sırasında denetlenmesi gerektiğini belirtir.

> **/ INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>Açıklamalar

DLL dosyasının veya yürütülebilir dosya üst bilgisinde, bu seçenek Windows görüntüyü yüklemek için bellek yöneticisi tarafından bir dijital imza denetimi gerektiren bir bayrak ayarlar. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yoksayın. Bu seçenek, çekirdek modu kodunu uygulayan ve tüm cihaz sürücüleri için tavsiye edilir 64-bit DLL'ler için ayarlanması gerekir. Daha fazla bilgi için [çekirdek modu kod imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)
