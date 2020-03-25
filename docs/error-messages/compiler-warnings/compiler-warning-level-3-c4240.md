---
title: Derleyici Uyarısı (düzey 3) C4240
ms.date: 11/04/2016
f1_keywords:
- C4240
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
ms.openlocfilehash: 9e4d33bd0151e4355903c7d10b667ced405a2471
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161574"
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
