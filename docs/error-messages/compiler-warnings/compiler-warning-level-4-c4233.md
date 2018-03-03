---
title: "Derleyici Uyarısı (düzey 4) C4233 | Microsoft Docs"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad27d2ec3d59df147d8bfc26372a2d25397e651f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4233"></a>Derleyici Uyarısı (düzey 4) C4233

> kullanılan standart olmayan uzantısı: '*anahtar sözcüğü*' C++, C değil yalnızca desteklenen anahtar sözcüğü

C++ yerine C olarak kaynak kodunuzu derleyici derlenmiş ve yalnızca C++'da geçerli bir anahtar sözcüğü kullanılır. Kaynak dosya uzantısını .c veya kullandığınız kaynak dosyanızı derleyici C derler [tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 4 uyarı sorunu yaşayıp C4233 yapmak için kaynak kodu dosyasına bu satırı ekleyin:

```cpp
#pragma warning(4:4233)
```
