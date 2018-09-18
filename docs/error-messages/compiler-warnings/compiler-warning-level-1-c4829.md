---
title: Derleyici Uyarısı (düzey 1) C4829 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4829
dev_langs:
- C++
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4210e8074360d5b3d5e5ca84e0326caf3303136
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065048"
---
# <a name="compiler-warning-level-1-c4829"></a>Derleyici Uyarısı (düzey 1) C4829

Büyük olasılıkla yanlış parametreler ana işlev. Göz önünde bulundurun ' intmain (Platform::Array\<Platform::String ^ > ^ argv)'

Bazı işlevler, ana gibi tür parametreleri başvuru alamıyor. Derleme başarılı olur, ancak elde edilen görüntü çalıştırma olmayabilir.

Aşağıdaki örnek, C4829 oluşturur:

```
// C4829.cpp
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp
int main(Platform::String ^ s) {}   // C4829

```