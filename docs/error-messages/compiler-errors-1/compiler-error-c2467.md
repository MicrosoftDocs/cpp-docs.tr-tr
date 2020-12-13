---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2467'
title: Derleyici hatası C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: fd5227e451208d848d631550da33999a4ebae8dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333816"
---
# <a name="compiler-error-c2467"></a>Derleyici hatası C2467

Anonim ' Kullanıcı tanımlı-tür ' bildirimi geçersiz

İç içe Kullanıcı tanımlı bir tür bildirildi. Bu, ANSI uyumluluk seçeneği ([/za](../../build/reference/za-ze-disable-language-extensions.md)) etkinken C kaynak kodu derlenirken bir hatadır.

Aşağıdaki örnek C2467 oluşturur:

```c
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```
