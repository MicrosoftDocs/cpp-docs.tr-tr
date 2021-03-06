---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4368'
title: Derleyici Uyarısı C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: 106d8b0bb0dc70f03017892e8597c0cf059016cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180792"
---
# <a name="compiler-warning-c4368"></a>Derleyici Uyarısı C4368

' Member ' yönetilen ' Type ' üyesi olarak tanımlanamaz: karma türler desteklenmiyor

Yerel bir veri üyesini bir CLR türüne katıştıramazsınız.

Ancak, yerel bir türe bir işaretçi bildirebilir ve yönetilen sınıfınızın oluşturucusunda ve yıkıcısında yaşam süresini kontrol edebilirsiniz. Daha fazla bilgi için bkz. [Yıkıcılar ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Bu uyarı her zaman bir hata olarak verilir. C4368 devre dışı bırakmak için [Warning](../../preprocessor/warning.md) pragma kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4368 oluşturur.

```cpp
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```
