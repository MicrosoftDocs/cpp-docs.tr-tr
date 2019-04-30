---
title: Derleyici Uyarısı (düzey 1) C4407
ms.date: 11/04/2016
f1_keywords:
- C4407
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
ms.openlocfilehash: 5142e3800f3ad716166a27e3b0407a40999b5746
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408413"
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