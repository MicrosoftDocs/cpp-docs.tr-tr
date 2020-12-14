---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3445'
title: Derleyici hatası C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 992c0e4f6e8b068bf6c038a6a5f58b45dd80a3c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316044"
---
# <a name="compiler-error-c3445"></a>Derleyici hatası C3445

> '*Type*' öğesinin kopya-liste başlatması açık bir Oluşturucu kullanamaz

ISO C++ 17 standardına göre, derleyici, Copy-List-Initialization içinde aşırı yükleme çözümlemesi için açık bir Oluşturucu kabul etmek zorundadır, ancak aşırı yükleme gerçekten seçilirse bir hata oluşturması gerekir.

Visual Studio 2017 ' den başlayarak, derleyici Visual Studio 2015 tarafından bulunamayan bir başlatıcı listesi kullanarak nesne oluşturmayla ilgili hataları bulur. Bu hatalar, çalışma zamanında kilitlenmelere veya tanımsız davranışlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3445 oluşturur.

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

Hatayı düzeltmek için, bunun yerine doğrudan başlatma kullanın:

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```
