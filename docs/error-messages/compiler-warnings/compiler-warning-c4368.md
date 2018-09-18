---
title: Derleyici Uyarısı C4368 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52026f08a56faa1372b73b94fe91c96682510038
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073219"
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