---
title: Derleyici Uyarısı (düzey 1) C4716 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4716
dev_langs:
- C++
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f7a6fd31ecae4643e947cb4a56897e80010e350
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093408"
---
# <a name="compiler-warning-level-1-c4716"></a>Derleyici Uyarısı (düzey 1) C4716

'function' bir değer döndürmelidir

Verilen işlevin bir değer döndürmedi.

Yalnızca işlevler dönüş türü void can ile eşlik eden bir dönüş değeri olmadan dönüş komutunu kullanın.

Bu işlev çağrıldığında, tanımlanmamış bir değer döndürülür.

Bu uyarı, bir hata için otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, [#pragma Uyarısı](../../preprocessor/warning.md).

Aşağıdaki örnek, C4716 oluşturur:

```
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```