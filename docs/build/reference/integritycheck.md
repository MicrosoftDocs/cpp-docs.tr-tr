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
ms.openlocfilehash: 4b0adf9add2d191ae89aec0a5d756ade8e9f7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370254"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

İkili görüntü dijital imzasını yükleme zamanında denetlenmesi gerektiğini belirtir.

> **/ INTEGRITYCHECK**[**: HAYIR**]

## <a name="remarks"></a>Açıklamalar

DLL dosyası veya yürütülebilir dosya üstbilgisinde, bu seçenek Windows görüntüsünü yüklemek için bellek yöneticisi tarafından bir dijital imza denetimi gerektirir bir bayrak ayarlar. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yok sayar. Bu seçenek, çekirdek modu kodu uygulamak ve tüm aygıt sürücülerini önerilen 64-bit DLL'ler için ayarlamanız gerekir. Daha fazla bilgi için bkz: [çekirdek modu kodu imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)  
