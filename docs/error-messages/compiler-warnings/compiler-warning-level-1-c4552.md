---
title: Derleyici Uyarısı (düzey 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 1fb2dc7fd4bc685e457898b47c513c21009146ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410362"
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