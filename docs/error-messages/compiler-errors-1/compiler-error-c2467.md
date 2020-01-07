---
title: Derleyici hatası C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: da17a3f78c8cab8144cb66b9a672dc59190b50f9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301151"
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
