---
title: Derleyici Hatası C3836 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a1349ff88c00f8091a8187bb963f4fb683b694e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046036"
---
# <a name="compiler-error-c3836"></a>Derleyici Hatası C3836

statik Oluşturucu üye başlatıcı listesi olmasına izin verilmiyor

Yönetilen bir sınıf üyesi başlatma listesi olan bir statik oluşturucu olamaz. Statik sınıf oluşturucuları başlatma statik veri üyeleri başlatma, sınıf için ortak dil çalışma zamanı tarafından çağrılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3836 oluşturur:

```
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```
