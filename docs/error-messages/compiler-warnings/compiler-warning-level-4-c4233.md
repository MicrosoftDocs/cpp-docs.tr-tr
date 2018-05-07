---
title: Derleyici Uyarısı (düzey 4) C4233 | Microsoft Docs
ms.custom: ''
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a933d41fd8e7cf3b94e458efff72193b8ce5e187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4233"></a>Derleyici Uyarısı (düzey 4) C4233

> kullanılan standart olmayan uzantısı: '*anahtar sözcüğü*' C++, C değil yalnızca desteklenen anahtar sözcüğü

C++ yerine C olarak kaynak kodunuzu derleyici derlenmiş ve yalnızca C++'da geçerli bir anahtar sözcüğü kullanılır. Kaynak dosya uzantısını .c veya kullandığınız kaynak dosyanızı derleyici C derler [tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarı sorunu yaşayıp C4233 yapmak için kaynak kodu dosyasına bu satırı ekleyin:

```cpp
#pragma warning(4:4233)
```
