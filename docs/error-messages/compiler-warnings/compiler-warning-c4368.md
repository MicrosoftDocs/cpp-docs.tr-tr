---
title: Derleyici Uyarısı C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: d96ae14bc427568dcf7ba7bc6e5d53f3d28883ae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165308"
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
