---
title: Derleyici Uyarısı (düzey 4) C4431 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4431
dev_langs:
- C++
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b44cd72548f88d922accfd571bd3ce9734b3a409
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034752"
---
# <a name="compiler-warning-level-4-c4431"></a>Derleyici Uyarısı (düzey 4) C4431

tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: Visual C++ artık oluşturur yazılmamış tanımlayıcıları int varsayılan olarak. Bir tanımlayıcı türünü açıkça belirtilmesi gerekir.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4431 oluşturur.

```
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```