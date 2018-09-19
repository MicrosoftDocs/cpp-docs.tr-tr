---
title: Derleyici Uyarısı (düzey 4) C4626 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4626
dev_langs:
- C++
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16ae3e9d9e54d54a419bfde2250fc02f780e8e54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083671"
---
# <a name="compiler-warning-level-4-c4626"></a>Derleyici Uyarısı (düzey 4) C4626

'derived class': atama işleci örtük bir şekilde bir taban sınıf atama işlecine erişilemez veya silinmiş olduğundan silindi olarak tanımlandı

Atama işleci, silinmiş veya taban sınıfında erişilebilir değil ve bir türetilmiş sınıf için oluşturulmadı. Bu tür nesneler atamak için her türlü girişim, bir derleyici hatasına neden olur.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4626 oluşturur ve bu sorunun nasıl gösterir:

```
// C4626
// compile with: /W4
#pragma warning(default : 4626)
class B
{
// public:
   B& operator = (const B&)
   {
      return *this;
   }
};

class D : public B
{

}; // C4626 - to fix, make B's copy constructor public

int main()
{
   D m;
   D n;
   // m = n;   // this line will cause an error
}
```