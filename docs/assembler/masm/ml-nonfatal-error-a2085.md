---
title: ML önemli olmayan hatası A2085 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd5ec9f36a4f956b8eeb097b6a8f8eaed89ba2b2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681442"
---
# <a name="ml-nonfatal-error-a2085"></a>ML Önemli Olmayan Hatası A2085

**yönerge veya kayıt geçerli CPU modunda kabul edilmedi**

Bir yönerge, kaydı veya geçerli işlemci modu için geçerli olmayan anahtar sözcük kullanmak için girişimde bulunuldu.

Örneğin, 32-bit kayıtlarını gerektiren [.386](../../assembler/masm/dot-386.md) veya üzeri. Denetim kayıtları CR0 kaydının gerektiren ayrıcalıklı modu gibi [.386P](../../assembler/masm/dot-386p.md) veya üzeri. Bu hata için de oluşturulacak **NEAR32**, **FAR32**, ve **DÜZ** gerekli anahtar sözcükleri. **386** veya üzeri.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>