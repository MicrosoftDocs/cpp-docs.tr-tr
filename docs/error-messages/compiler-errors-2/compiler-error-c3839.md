---
title: Derleyici hatası C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: 19a1055a461d76856cc3bccbd9f8af0f0dcff356
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754933"
---
# <a name="compiler-error-c3839"></a>Derleyici hatası C3839

yönetilen veya WinRT türünde hizalama değiştirilemez

Yönetilen veya Windows Çalışma Zamanı türlerindeki değişkenlerin hizalaması CLR veya Windows Çalışma Zamanı tarafından denetlenir ve [align](../../cpp/align-cpp.md)ile değiştirilemez.

Aşağıdaki örnek C3839 oluşturur:

```cpp
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```
