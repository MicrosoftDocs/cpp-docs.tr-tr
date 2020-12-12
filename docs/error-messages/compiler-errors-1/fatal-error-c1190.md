---
description: 'Daha fazla bilgi edinin: önemli hata C1190'
title: Önemli hata C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: e351a04d548816999d61973276203d34745c0a75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123610"
---
# <a name="fatal-error-c1190"></a>Önemli hata C1190

yönetilen hedeflenen kod bir '/CLR ' seçeneği gerektiriyor

CLR yapılarını kullanıyorsunuz, ancak **/clr** belirtmadınız.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

Aşağıdaki örnek C1190 oluşturur:

```cpp
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```
