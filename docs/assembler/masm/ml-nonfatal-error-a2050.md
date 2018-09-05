---
title: ML önemli olmayan hatası A2050 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd2e0e6c2fc818ef9286fd303c07a26bdd8b4e5a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680677"
---
# <a name="ml-nonfatal-error-a2050"></a>ML Önemli Olmayan Hatası A2050

**Gerçek veya BCD sayı izin verilmiyor**

(Gerçek) kayan noktalı sayı veya İkili Kodlanmış Ondalık (BCD) sabiti dışında kullanılan veri başlatıcı olarak.

Aşağıdakilerden biri oluştu:

- Bir gerçek sayı veya bir BCD bir ifade kullanıldı.

- Bir gerçek sayı bir yönerge dışında başlatmak için kullanılan [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), veya [TBYTE](../../assembler/masm/tbyte.md).

- Bir yönerge dışında başlatmak için kullanılan bir BCD `TBYTE`.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>