---
title: ML Önemli Hatası A1007
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 98933c3a24da22f447174a3b51c4855690aba83e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177909"
---
# <a name="ml-fatal-error-a1007"></a>ML Önemli Hatası A1007

**çok derin iç içe geçme düzeyi**

Derleyici iç içe geçme sınırına ulaşıldı. Tersi belirtilmedikçe hariç 20 düzeyleri sınırlıdır.

Aşağıdakilerden biri çok derin iç içe geçmiş:

- Gibi üst düzey bir yönerge [. Eğer](../../assembler/masm/dot-if.md), [. Yineleme](../../assembler/masm/dot-repeat.md), veya [. SIRADA](../../assembler/masm/dot-while.md).

- Bir yapı tanımı.

- Bir koşullu derleme yönergesi.

- Bir yordamı tanımı.

- A [PUSHCONTEXT](../../assembler/masm/pushcontext.md) yönergesi (sınır: 10).

- Segment tanımı.

- Bir ekleme dosyası.

- Makro.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>