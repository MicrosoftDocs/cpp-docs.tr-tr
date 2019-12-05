---
title: ML Önemli Hatası A1007
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 01633b4fa084b7d5e14af5a5c6e51e3dca684d2a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856923"
---
# <a name="ml-fatal-error-a1007"></a>ML Önemli Hatası A1007

**iç içe geçme düzeyi çok derin**

Derleyici, iç içe geçmiş sınırına ulaştı. Sınır, aksi belirtilmedikçe 20 düzeydir.

Aşağıdakilerden biri çok derin iç içe geçmiş:

- Gibi üst düzey bir yönerge [. Ise](../../assembler/masm/dot-if.md), [. Veya TEKRARLAYıN](../../assembler/masm/dot-repeat.md) [. WHILE](../../assembler/masm/dot-while.md).

- Bir yapı tanımı.

- Koşullu derleme yönergesi.

- Bir yordam tanımı.

- Bir [PushContext](../../assembler/masm/pushcontext.md) yönergesi (sınır 10 ' dur).

- Bir segment tanımı.

- Bir içerme dosyası.

- Bir makro.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>