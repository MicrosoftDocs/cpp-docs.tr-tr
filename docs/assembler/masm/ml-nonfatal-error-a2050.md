---
title: ML Önemli Olmayan Hatası A2050
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 15c6449ff4207c92dee28120d4f61be641cf01c8
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856583"
---
# <a name="ml-nonfatal-error-a2050"></a>ML Önemli Olmayan Hatası A2050

**gerçek veya BCD numarasına izin verilmiyor**

Bir kayan nokta (gerçek) numarası veya ikili kodlu ondalık (BCD) sabiti, veri başlatıcısı olarak dışında kullanıldı.

Aşağıdakilerden biri oluştu:

- Bir ifadede gerçek sayı veya BCD kullanıldı.

- [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md)veya [TByte](../../assembler/masm/tbyte.md)dışında bir yönergeyi başlatmak için gerçek bir sayı kullanıldı.

- `TBYTE`dışındaki bir yönergeyi başlatmak için bir BCD kullanıldı.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>