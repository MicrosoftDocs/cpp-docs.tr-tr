---
title: 'Hata: Geçersiz ayırma hizalaması'
description: Kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri geçersiz _aligned_malloc hatalarına yöneliktir.
ms.date: 03/02/2021
f1_keywords:
- invalid-allocation-alignment
helpviewer_keywords:
- invalid-allocation-alignment error
- AddressSanitizer error invalid-allocation-alignment
ms.openlocfilehash: 99318b068c2908bbe9eee63bef80c5f3f5e37e75
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470654"
---
# <a name="error-invalid-allocation-alignment"></a>Hata: `invalid-allocation-alignment`

> Adres temizleme hatası: Geçersiz ayırma hizalaması

[`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md)İşlevin, hizalamayı ifade etmek için 2 ' nin üssü olması gerekir. En iyi duruma getirilmiş bir genel değişken kullanarak bazı hizalama faktörünün "dış" hesaplamasının benzetimini yaptık.

## <a name="example"></a>Örnek

```cpp
// example1.cpp
// invalid-allocation-alignment error
#include <Windows.h>

int ExternalAlign = 5;

int main(){

    // this externally calculated alignment of 5 isn't valid.

    void* ptr = _aligned_malloc(8,ExternalAlign); 
    return (ptr == nullptr && errno == EINVAL) ? 0 : -1;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/invalid-allocation-alignment-example-1.png" alt-text="Örnek 1 ' de geçersiz ayırma hizalama hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
