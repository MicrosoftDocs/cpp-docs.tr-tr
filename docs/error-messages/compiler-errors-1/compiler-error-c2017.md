---
title: Derleyici Hatası C2017 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2017
dev_langs:
- C++
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f547501ab399165fe256f0dc3d0423b3569c05e7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062208"
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