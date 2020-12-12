---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2588'
title: Derleyici hatası C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 7f723f826a5d4e609c0766c5287a0fffdee72d18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177581"
---
# <a name="compiler-error-c2588"></a>Derleyici hatası C2588

':: ~ Identifier ': geçersiz genel yıkıcı

Yıkıcı, bir sınıf, yapı veya birleşim dışında bir öğe için tanımlanır. Buna izin verilmez.

Bu hata, kapsam çözümleme () işlecinin sol tarafındaki eksik bir sınıf, yapı veya birleşim adından kaynaklanıyor olabilir `::` .

Aşağıdaki örnek C2588 oluşturur:

```cpp
// C2588.cpp
~F();   // C2588
```
