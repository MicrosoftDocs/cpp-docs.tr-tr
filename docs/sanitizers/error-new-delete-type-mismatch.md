---
title: 'Hata: New-delete-type-uyuşmazlık'
description: Yeni silme türü uyuşmazlığı hataları için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- new-delete-type-mismatch
helpviewer_keywords:
- new-delete-type-mismatch error
- AddressSanitizer error new-delete-type-mismatch
ms.openlocfilehash: 02ea69b16fbb18878fd46544488ac8f3e0d4e3b5
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470665"
---
# <a name="error-new-delete-type-mismatch"></a>Hata: `new-delete-type-mismatch`

> Adres temizleme hatası: ayırma boyutundan farklı olan boyutu kaldırma

Bu örnekte, yalnızca `~Base` , ve değil olarak `~Derived` adlandırılır. `~Base()`Yok edicisi olmadığından, derleyici öğesine bir çağrı oluşturur `Base` **`virtual`** . `delete b`' İ çağırdığınızda, nesnenin yıkıcısı varsayılan tanıma bağlanır. Kod boş bir temel sınıfı siler (veya Windows üzerinde 1 bayt). **`virtual`** Yıkıcı bildiriminde eksik bir anahtar sözcük, devralma kullanılırken yaygın bir C++ hatasıdır.

## <a name="example---virtual-destructor"></a>Örnek-sanal yıkıcı

```cpp
// example1.cpp
// new-delete-type-mismatch error
#include <memory>
#include <vector>

struct T {
    T() : v(100) {}
    std::vector<int> v;
};

struct Base {};

struct Derived : public Base {
    T t;
};

int main() {
    Base *b = new Derived;

    delete b;  // Boom! 

    std::unique_ptr<Base> b1 = std::make_unique<Derived>();

    return 0;
}
```

Polimorfik temel sınıflar **`virtual`** yıkıcıları bildirmelidir. Bir sınıfta sanal işlevler varsa, sanal bir yıkıcıya sahip olmalıdır.

Örneği onarmak için şunu ekleyin:

```cpp
struct Base {
  virtual ~Base() = default;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/new-delete-type-mismatch-example-1.png" alt-text="Örnek 1 ' de New-delete-type-uyuşmazlığını görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
