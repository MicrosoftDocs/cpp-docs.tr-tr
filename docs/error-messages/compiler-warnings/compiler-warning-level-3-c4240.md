---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4240'
title: Derleyici Uyarısı (düzey 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: 95e704b6ad91ff77c4def0b4fa1fe8fad002e5ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344204"
---
# <a name="compiler-warning-level-3-c4240"></a>Derleyici Uyarısı (düzey 3) C4240

Standart olmayan uzantı kullanıldı: ' ClassName ' erişimi artık ' erişim belirticisi ' olarak tanımlandı, daha önce ' erişim belirticisi ' olarak tanımlandı

ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında, iç içe bir sınıfa erişimi değiştiremezsiniz. Varsayılan Microsoft uzantıları (/Ze) altında, Bu uyarıyla yapabilirsiniz.

## <a name="example"></a>Örnek

```cpp
// C4240.cpp
// compile with: /W3
class X
{
private:
   class N;
public:
   class N
   {   // C4240
   };
};

int main()
{
}
```
