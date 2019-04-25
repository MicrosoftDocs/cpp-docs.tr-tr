---
title: Derleyici Hatası C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 22ecc176036308699c3ad7bd8c015836be910073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174219"
---
# <a name="compiler-error-c3161"></a>Derleyici Hatası C3161

'interface': iç içe sınıf, yapı, birleşim veya bir arabirim içindeki arabirim; geçersiz Arabirim içinde sınıf, yapı veya birleşim geçersizdir

Bir [__interface](../../cpp/interface.md) yalnızca genel kapsamda veya ad alanı içinde yer alabilir. Bir sınıf, yapı veya birleşim arabirim içinde yer alamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3161 oluşturur.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```