---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4632'
title: Derleyici Uyarısı (düzey 1) C4632
ms.date: 11/04/2016
f1_keywords:
- C4632
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
ms.openlocfilehash: a055f49a1aa71c36679f7c6177f502141e52dcde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318877"
---
# <a name="compiler-warning-level-1-c4632"></a>Derleyici Uyarısı (düzey 1) C4632

XML belgesi açıklaması: dosya erişimi reddedildi: neden

. Xdc dosyasının ( `file` ) yolu geçerli değil ve. xdc dosyası oluşturulmadı.

Aşağıdaki örnek C4632 oluşturur:

```cpp
// C4632.cpp
// compile with: /clr /docv:\\falsedir /LD /W1
// C4632 expected

/// Text for class MyClass.
public ref class MyClass {};
```
