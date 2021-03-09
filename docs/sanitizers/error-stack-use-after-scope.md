---
title: 'Hata: yığın kullanımı-sonrası-kapsam'
description: Kapsam hatalarından sonra yığın kullanımı için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 02/05/2021
f1_keywords:
- stack-use-after-scope
helpviewer_keywords:
- stack-use-after-scope error
- AddressSanitizer error stack-use-after-scope
ms.openlocfilehash: 2b6e3ada1cc5b76b371e8059e045735b16d4b334
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470645"
---
# <a name="error-stack-use-after-scope"></a>Hata: `stack-use-after-scope`

> Adres temizleme hatası: kapsam dışı yığın belleği kullanımı

Bir değişkenin yaşam süresinden oluşan sözcük kapsamı dışında bir yığın adresinin kullanılması, C veya C++ ' da birçok yol ortaya çıkabilir.

## <a name="example-1---simple-nested-local"></a>Örnek 1-basit iç içe yerel

```cpp
// example1.cpp
// stack-use-after-scope error
int *gp;

bool b = true;

int main() {
    if (b) {
        int x[5];
        gp = x+1;
    }
    return *gp;  // Boom!
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error---simple-nested-local"></a>Ortaya çıkan hata-basit iç içe yerel

:::image type="content" source="media/stack-use-after-scope-example-1.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcı örnek 1 ' de ekran görüntüsü.":::

## <a name="example-2---lambda-capture"></a>Örnek 2-Lambda yakalama

```cpp
// example2.cpp
// stack-use-after-scope error
#include <functional>

int main() {
    std::function<int()> f;
    {
        int x = 0;
        f = [&x]() {
            return x;  // Boom!
        };
    }
    return f();  // Boom!
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---lambda-capture"></a>Ortaya çıkan hata-Lambda yakalama

:::image type="content" source="media/stack-use-after-scope-example-2.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcının ekran görüntüsü örnek 2.":::

## <a name="example-3---destructor-ordering-with-locals"></a>Örnek 3-Yereller içeren yıkıcıyı verme

```cpp
// example3.cpp
// stack-use-after-scope error
#include <stdio.h>

struct IntHolder {
    explicit IntHolder(int* val = 0) : val_(val) { }
    ~IntHolder() {
        printf("Value: %d\n", *val_);  // Bom!
    }
    void set(int* val) { val_ = val; }
    int* get() { return val_; }

    int* val_;
};

int main(int argc, char* argv[]) {
    // It's incorrect to use "x" inside the IntHolder destructor,
    // because the lifetime of "x" ends earlier. Per the C++ standard,
    // local lifetimes end in reverse order of declaration.
    IntHolder holder;
    int x = argc;
    holder.set(&x);
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi /O1
devenv /debugexe example3.exe
```

### <a name="resulting-error---destructor-ordering"></a>Sonuç hatası-yıkıcı sıralaması

:::image type="content" source="media/stack-use-after-scope-example-3.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcının ekran görüntüsü örnek 3.":::

## <a name="example-4---temporaries"></a>Örnek 4-geçiciler

```cpp
// example4.cpp
// stack-use-after-scope error
#include <iostream>

struct A {
    A(const int& v) {
        p = &v;
    }
    void print() {
        std::cout << *p;
    }
    const int* p;
};

void explicit_temp() {
    A a(5);     // the temp for 5 is no longer live;
    a.print();
}

void temp_from_conversion() {
    double v = 5;
    A a(v);     // local v is no longer live.
    a.print();
}

void main() {
    explicit_temp();
    temp_from_conversion(); 
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example4.cpp /EHsc /fsanitize=address /Zi
devenv /debugexe example4.exe
```

### <a name="resulting-error---temporaries"></a>Sonuç hatası-geçiciler

:::image type="content" source="media/stack-use-after-scope-example-4.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcının ekran görüntüsü örnek 4 ' te.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
