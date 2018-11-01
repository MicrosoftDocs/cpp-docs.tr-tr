---
title: Derleyici Hatası C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596787"
---
# <a name="compiler-error-c2588"></a>Derleyici Hatası C2588

':: ~ tanımlayıcı ': Geçersiz Genel yok Edicisi

Yıkıcı bir şey için bir sınıf, yapı veya birleşim dışında tanımlanır. Buna izin verilmez.

Eksik sınıf, yapı veya birleşim adı kapsam çözünürlük sol tarafındaki bu hataya neden olabilir (`::`) işleci.

Aşağıdaki örnek, C2588 oluşturur:

```
// C2588.cpp
~F();   // C2588
```