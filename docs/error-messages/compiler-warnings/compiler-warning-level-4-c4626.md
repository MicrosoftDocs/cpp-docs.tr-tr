---
title: Derleyici Uyarısı (düzey 4) C4626
ms.date: 11/04/2016
f1_keywords:
- C4626
helpviewer_keywords:
- C4626
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
ms.openlocfilehash: cb00365d12a60885a86a42417bf1c1052a5c6d6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538560"
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