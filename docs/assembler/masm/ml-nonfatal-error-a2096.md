---
title: ML önemli olmayan hatası A2096 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f4ef76dca10b1208a931bc3e1cc09d82a639d2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679604"
---
# <a name="ml-nonfatal-error-a2096"></a>ML Önemli Olmayan Hatası A2096

**Segment, Grup veya segment kaydı bekleniyordu**

Segment veya grup bekleniyordu ancak bulunamadı.

Aşağıdakilerden biri oluştu:

- Sol işlenen kesimle belirtilen geçersiz kılma işleci (**:**) bir segment yazmaç (CS, DS, SS, ES, FS veya GS), grup adı, segment adı veya segment ifade değildi.

- [VARSAY](../../assembler/masm/assume.md) yönergesi dikkate alındığında bir segment kayıt olmadan geçerli kesim adresi, segment kaydetme, Grup veya özel **DÜZ** grubu.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>