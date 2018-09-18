---
title: Derleyici Uyarısı (düzey 1) C4552 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4552
dev_langs:
- C++
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62c08ea81f5f8794a1dd4ff7d0b5644e9a669e0f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048077"
---
# <a name="compiler-warning-level-1-c4552"></a>Derleyici Uyarısı (düzey 1) C4552

'operator': işlecin etkisi yok; yan etkisi olan beklenen işleci

Bir ifade deyimi ifade üstüne yan etkiye sahip bir işleç varsa, bir hata olabilir.

Bu uyarıyı geçersiz kılmak için ifadeyi parantez içine yerleştirin.

Aşağıdaki örnek, C4552 oluşturur:

```
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```