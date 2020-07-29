---
title: /Zc:alignedNew (C++17 aşırı hizalanmış ayırma)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: f036c2d7bc4619685d2763702f447476e8e1a1e4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217200"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C++17 aşırı hizalanmış ayırma)

**`new`** En büyük ölçekli standart hizalanmış tür için varsayılandan daha büyük sınırlar üzerinde hizalı, dinamik bellek ayırma desteğini etkinleştirin. ** \_ \_ **

## <a name="syntax"></a>Sözdizimi

> **/Zc: alignedNew** \[ -]

## <a name="remarks"></a>Açıklamalar

MSVC derleyicisi ve kitaplığı, C++ 17 standart hizalanmış dinamik bellek ayırmayı destekler. **/Zc: alignedNew** seçeneği belirtildiğinde, `new Example;` her bir *Example* `max_align_t` temel tür için gereken en büyük hizalamanın büyük olduğu durumlarda bile bir dinamik ayırma, örneğin hizalamasını uyar. Ayrılmış türün hizalaması, orijinal operatör tarafından garantiden daha fazla olmadığında **`new`** , önceden tanımlanmış makro ** \_ \_ stdcpp \_ varsayılan \_ Yeni \_ \_ \_ Hizalama**değeri olarak kullanılabilir, ifade `new Example;` `::operator new(size_t)` c++ 14 ' te olduğu gibi bir çağrıya neden olur. Hizalama, ** \_ \_ stdcpp \_ varsayılan \_ Yeni \_ hizalamadan \_ \_ **büyükse, bunun yerine, kullanarak belleği alır `::operator new(size_t, align_val_t)` . Benzer şekilde, fazla hizalanmış türlerin silinmesi `::operator delete(void*, align_val_t)` veya boyutlandırılmış silme imzasını çağırır `::operator delete(void*, size_t, align_val_t)` .

**/Zc: alignedNew** seçeneği yalnızca [/std: c++ 17](std-specify-language-standard-version.md) veya [/std: c + + latest](std-specify-language-standard-version.md) etkin olduğunda kullanılabilir. **/Std: c++ 17** veya **/std: c + + latest**, **/Zc: ALIGNEDNEW** , varsayılan olarak ISO c++ 17 standardına uyacak şekilde etkindir. Yalnızca işlecini uygularsanız **`new`** ve **`delete`** üzerinde hizalanmış ayırmaları desteklemek istiyorsanız, bu koda c++ 17 modunda gerek kalmaz. Bu seçeneği devre dışı bırakmak ve C++ 14 davranışına dönmek için **`new`** ve **`delete`** **/std:: c++ 17** veya **/std: C + + en son**sürümünü kullandığınızda **/Zc: alignednew-** belirtin. İşlecini uygular **`new`** **`delete`** , ancak parametresi olan aşırı hizalanmış işleç **`new`** ve **`delete`** aşırı yüklemeleri uygulamaya hazırsanız `align_val_t` , derleyicinin ve standart kitaplığın daha fazla hizalanmış aşırı yüklemeye çağrı oluşturmasını engellemek Için **/Zc: alignednew-** seçeneğini kullanın. [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: alignednew**varsayılan ayarını değiştirmez.

**/ZC desteği: alignedNew** , Visual Studio 2017 sürüm 15,5 ' den başlayarak kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek **`new`** **`delete`** , **/Zc: alignednew** seçeneği ayarlandığında işlecin ve işlecin nasıl davrandığını gösterir.

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

Bu çıktı 32 bitlik derlemeler için tipik bir davranıştır. İşaretçi değerleri, uygulamanızın bellekte çalıştığı yere göre farklılık gösterir.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: alignednew** veya **/Zc: alignednew** ' i içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
