---
title: / INTEGRITYCHECK | Microsoft Docs
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99caec18162a7506b8b7a467eb7374b6fe4a38d9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

İkili görüntü dijital imzasını yükleme zamanında denetlenmesi gerektiğini belirtir.

> **/ INTEGRITYCHECK**[**: HAYIR**]

## <a name="remarks"></a>Açıklamalar

DLL dosyası veya yürütülebilir dosya üstbilgisinde, bu seçenek Windows görüntüsünü yüklemek için bellek yöneticisi tarafından bir dijital imza denetimi gerektirir bir bayrak ayarlar. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yok sayar. Bu seçenek, çekirdek modu kodu uygulamak ve tüm aygıt sürücülerini önerilen 64-bit DLL'ler için ayarlamanız gerekir. Daha fazla bilgi için bkz: [çekirdek modu kodu imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)  
