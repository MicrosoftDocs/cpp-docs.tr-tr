---
title: Derleyici Uyarısı (düzey 1) C4407 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4407
dev_langs:
- C++
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9a665dbb71157b37f72d3d0721357d00dc37230
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032611"
---
# <a name="compiler-warning-level-1-c4407"></a>Derleyici Uyarısı (düzey 1) C4407

farklı işaretçiden üyeye gösterimleri arasında tür dönüştürme; derleyici yanlış kod üretebilir

Hatalı bir tür dönüştürme algılandı.

Visual C++ 2005'te yapıldığı derleyici uyumluluğu iş nedeniyle C4407 oluşturulabilir. İşaretçi-üye artık gerektiren bir tam adı ve address-of işleci (&).

Bir çoklu devralma işaretçi-üye için bir tek devralma işaretçi-üye arasında dönüştürme C4407 oluşabilir. Bu bazen çalışabilir, ancak bazen tek devralma işaretçi-üye gösterimi yeterli bilgiyi tutmak değil olduğundan işlem gerçekleştirilemiyor. İle derlerken **/VMM** yardımcı olabilir (daha fazla bilgi için [/VMM, / VMs, / vmv (genel amaçlı temsil)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Taban sınıfları yeniden düzenleme de deneyebilirsiniz; sıfır olmayan uzaklığı türetilmiş bir temel sınıf olduğundan derleyici dönüştürmede bilgi kaybı algılıyor.

Aşağıdaki örnek, C4407 oluşturur:

```
// C4407.cpp
// compile with: /W1 /c
struct C1 {};
struct C2 {};
struct C3 : C1, C2 {};

typedef void(C3::*PMF_C3)();
typedef void(C2::*PMF_C2)();

PMF_C2 f1(PMF_C3 pmf) {
   return (PMF_C2)pmf;   // C4407, change type of cast,
   // or reverse base class inheritance of C3 (i.e. : C2, C1)
}
```