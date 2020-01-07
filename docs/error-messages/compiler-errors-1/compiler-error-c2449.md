---
title: Derleyici hatası C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: 6fd62813fdf3b50c0e329fc423e100d55a36ae12
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299029"
---
# <a name="compiler-error-c2449"></a>Derleyici hatası C2449

Dosya kapsamında ' {' bulundu (işlev üstbilgisi eksik mi?)

Dosya kapsamında açık bir ayraç oluşur.

Bu hata, bir işlev üst bilgisi ve işlev tanımının açma ayracı arasında noktalı virgülden kaynaklanıyor olabilir.

Aşağıdaki örnek C2499 oluşturur:

```c
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```
