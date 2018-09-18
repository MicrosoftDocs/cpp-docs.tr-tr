---
title: Derleyici Hatası C3183 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3183
dev_langs:
- C++
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76822882f1b0ac2da2e18131b47d5730820f4751
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020192"
---
# <a name="compiler-error-c3183"></a>Derleyici Hatası C3183

Adsız sınıf, yapı veya birleşim tanımlanamaz içinde yönetilen veya WinRT ' type'

Katıştırılmış bir türü bir yönetilen veya WinRT türü olarak adlandırılmalıdır.

Aşağıdaki örnek, C3183 oluşturur:

```
// C3183a.cpp
// compile with: /clr /c
ref class Test
{
   ref class
   {  // C3183, delete class or name it
      int a;
      int b;
   };
};
```
