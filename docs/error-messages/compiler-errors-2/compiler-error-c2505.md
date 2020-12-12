---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2505'
title: Derleyici hatası C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: 46054594731b8e39f4cb4b13e71559fcdbd2a55d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213019"
---
# <a name="compiler-error-c2505"></a>Derleyici hatası C2505

' symbol ': ' __declspec (modifer) ' yalnızca genel nesnelerin veya statik veri üyelerinin bildirimlerine veya tanımlarına uygulanabilir

**`__declspec`** Yalnızca genel kapsamda kullanılmak üzere tasarlanan bir değiştirici bir işlevde kullanıldı.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [Process](../../cpp/process.md).

Aşağıdaki örnek C2505 oluşturur:

```cpp
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```
