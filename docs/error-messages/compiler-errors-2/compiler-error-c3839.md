---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3839'
title: Derleyici hatası C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: 8b34cdd7f09bea924d3e184f7ea639c3f8210ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180805"
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
