---
title: Derleyici Hatası C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 2eddeb5a56c953ca0864e29187fbe28c53bdee24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328659"
---
# <a name="compiler-error-c3445"></a>Derleyici Hatası C3445

> kopya listesi başlatmasında, '*türü*' açık bir Oluşturucu kullanılamaz

Derleyici ISO C ++ 17 standardına göre açık bir oluşturucu aşırı yükleme çözünürlüğü içinde kopya listesi başlatması için göz önünde bulundurmanız gereken ancak aşırı yükleyen gerçekten seçilirse hata yükseltmeniz gerekir.

Visual Studio 2017'den itibaren derleyici bir başlatıcı listesi kullanılarak nesne oluşturma ilgili olan ve Visual Studio 2015 tarafından bulunamadı hataları bulur. Bu hatalar sistem çökmeleri ya da çalışma zamanında tanımsız davranışa neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3445 oluşturur.

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

Hatayı düzeltmek için bunun yerine doğrudan başlatma kullanın:

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
