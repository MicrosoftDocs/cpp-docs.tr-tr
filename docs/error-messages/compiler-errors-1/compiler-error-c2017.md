---
title: Derleyici Hatası C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: f4a17557e5e4ca1eb3f69561c964c9bbe24bb70d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440371"
---
# <a name="compiler-error-c2017"></a>Derleyici Hatası C2017

Geçersiz kaçış sırası

Bir karakter veya dize dışında \t'gibi bir kaçış dizisi görünür sabit.

Aşağıdaki örnek, C2017 oluşturur:

```
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017 stringize işleci kaçış dizileri içeren dizelerle kullanıldığında ortaya çıkabilir.

Aşağıdaki örnek, C2017 oluşturur:

```
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```