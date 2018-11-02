---
title: Nesnelerin Kaynakları (RAII)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
ms.openlocfilehash: a10d6c2177c391ead6065767994b09fb6236ee3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593618"
---
# <a name="objects-own-resources-raii"></a>Nesnelerin Kaynakları (RAII)

Kendi kaynaklarını nesnelerin emin olun. Bu ilke olarak da bilinen "kaynak alımı başlatma" ise veya "RAII."

## <a name="example"></a>Örnek

"Yeni" her nesne (hemen her zaman unique_ptr) sahip başka bir adlandırılmış nesnesi bir oluşturucu bağımsız değişken olarak geçirin.

```cpp
void f() {
    unique_ptr<widget> p( new widget() );
    my_class x( new widget() );
    // ...
} // automatic destruction and deallocation for both widget objects
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"
```

Her zaman hemen yeni bir kaynak sahibi başka bir nesneye geçirin.

```cpp
void g() {
    other_class y( OpenFile() );
    // ...
} // automatic closing and release for file resource
  // automatic exception safety, as if "finally { y.file.dispose(); }"
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)