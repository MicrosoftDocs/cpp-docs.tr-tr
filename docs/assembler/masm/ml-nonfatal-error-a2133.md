---
title: ML önemli olmayan hatası A2133 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0df094f5e7135ffb3b9a5f09383e03e411755de3
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678072"
---
# <a name="ml-nonfatal-error-a2133"></a>ML Önemli Olmayan Hatası A2133

**değere göre Çağır üzerine kaydetme**

Bir kayıt için bir yordam bağımsız değişken olarak geçirildi, ancak kod tarafından oluşturulan [INVOKE](../../assembler/masm/invoke.md) diğer bağımsız değişkenleri geçirmek için kayıt içeriğini yok.

AX, AL, AH, EAX, DX, DL, DH ve EDX yazmaçlarına, veri dönüştürme yapmak için derleyici tarafından kullanılıyor olabilir.

Farklı bir kayıt kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>