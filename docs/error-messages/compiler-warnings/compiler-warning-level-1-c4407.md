---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4407'
title: Derleyici Uyarısı (düzey 1) C4407
ms.date: 11/04/2016
f1_keywords:
- C4407
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
ms.openlocfilehash: ea743c5df5f84e99ad89e44a08844b3e59593c1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311103"
---
# <a name="compiler-warning-level-1-c4407"></a>Derleyici Uyarısı (düzey 1) C4407

farklı işaretçilere üye temsillerine atama, derleyici yanlış kod üretebilir

Yanlış bir atama algılandı.

C4407, Visual Studio 2005 ' de gerçekleştirilen derleyici uyumluluğu işi nedeniyle oluşturulabilir. Üye işaretçisi artık nitelenmiş bir ad ve adres işleci (&) gerektirir.

Birden çok devralım işaretçisi arasında tek bir devralma işaretçisine üye olarak atama yaparsanız, C4407 oluşabilir. Bazen bu işe yarar, ancak tek bir devralma işaretçisinin üye gösteriminin yeterli bilgi içermediğinden, bazı durumlarda olamaz. **/VMM** ile derleme yardımcı olabilirler (daha fazla bilgi için bkz. [/VMM,/VM 'ler,/vmv (genel amaçlı temsili)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Ayrıca, temel sınıflarınızı yeniden düzenlemeyi deneyebilirsiniz; Derleyici, bir taban sınıfı türetilmişten sıfır olmayan bir uzaklığa sahip olduğundan, dönüştürmede bilgi kaybını algılıyor.

Aşağıdaki örnek C4407 oluşturur:

```cpp
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
