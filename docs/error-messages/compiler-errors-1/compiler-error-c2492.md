---
title: Derleyici Hatası C2492 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fcb9058bf1aac584e8b7728616f821bda4b33f6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096281"
---
# <a name="compiler-error-c2492"></a>Derleyici Hatası C2492

'*değişkeni*': iş parçacığı depolama süresine sahip verilerin dll arabirimi olmayabilir

Değişkeni ile bildirilen [iş parçacığı](../../cpp/thread.md) özniteliği ve DLL ile arabirim. Adresini `thread` değişkeni için bir DLL içeri veya dışarı aktarma bağlanamaz için çalışma zamanına kadar tanınmıyor.

Aşağıdaki örnek, C2492 oluşturur:

```
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```