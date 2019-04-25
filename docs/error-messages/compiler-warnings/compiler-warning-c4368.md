---
title: Derleyici Uyarısı C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: b2af1166738d867c84ff4ebae832f831af7940ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311507"
---
# <a name="compiler-warning-c4368"></a>Derleyici Uyarısı C4368

'member' yönetilen 'type' üyesi olarak tanımlanamaz: karma türler desteklenmiyor

Bir CLR türü bir yerel veri üyesi katıştırılamıyor.

Bununla birlikte, yerel bir tür işaretçisi bildirmek ve ömrü oluşturucusu ve yıkıcısı yönetilen sınıfınızın Sonlandırıcı denetleyebilirsiniz. Daha fazla bilgi için [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Bu uyarı, her zaman hata olarak görüntülenir. Kullanım [uyarı](../../preprocessor/warning.md) pragma C4368 devre dışı bırakmak için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4368 oluşturur.

```
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