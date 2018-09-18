---
title: Derleyici Hatası C3839 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 597d02ff347d399833e2376743b50f65e7674a18
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092914"
---
# <a name="compiler-error-c3839"></a>Derleyici Hatası C3839

yönetilen bir hizalama veya WinRT türü değiştirilemiyor

Değişkenleri hizalamasını yönetilen veya Windows çalışma zamanı türleri CLR ya da Windows çalışma zamanı tarafından denetlenir ve ile değiştirilemez [hizalama](../../cpp/align-cpp.md).

Aşağıdaki örnek, C3839 oluşturur:

```
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