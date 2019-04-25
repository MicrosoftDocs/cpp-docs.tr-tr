---
title: Önemli hata C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228911"
---
# <a name="fatal-error-c1190"></a>Önemli hata C1190

Yönetilen hedeflenen kod gerektiren bir ' / clr' seçeneği

CLR yapıları kullanıyor, ancak sizin belirtmediğiniz **/CLR**.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

Aşağıdaki örnek, C1190 oluşturur:

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```