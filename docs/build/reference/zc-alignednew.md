---
title: /Zc:alignedNew (C++17 aşırı hizalanmış ayırma)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: 041f62bbbf5f7a2750960d21d1534cf6daf4b874
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335691"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C++17 aşırı hizalanmış ayırma)

C++17 için desteği etkinleştirin aşırı hizalanmış **yeni,** dinamik bellek ayırma sınırları maksimum boyutlu standart hizalanmış türü için varsayılandan daha büyük hizalanmış, **max\_align\_t**.

## <a name="syntax"></a>Sözdizimi

> **/Zc:alignedYeni**\[-]

## <a name="remarks"></a>Açıklamalar

MSVC derleyicisi ve kitaplık C++17 standart aşırı hizalanmış dinamik bellek ayırmayı destekler. **/Zc:alignedNew** seçeneği belirtildiğinde, herhangi bir `new Example;` temel tür için gereken en büyük hizalamadan daha büyük `max_align_t`olsa bile *Örnek'in* hizalanmasına saygı gösterin gibi dinamik bir ayırma. Ayrılan türün hizalaması, önceden tanımlanmış makro `new Example;` `::operator new(size_t)` ** \_ \_STDCPP\_DEFAULT\_YENİ\_HIZALAMA\_** değeri olarak kullanılabilir orijinal işleç **tarafından**garanti edilen hizalama dan daha fazla olmadığında, ekstre C++14'te olduğu gibi bir çağrıyla sonuçlanır. Hizalama ** \_ \_STDCPP\_VARSAYıLAN\_Yenİ\_HIZALAMA\_** daha büyük olduğunda, uygulama yerine kullanarak `::operator new(size_t, align_val_t)`bellek elde eder. Benzer şekilde, aşırı hizalanmış türleri silme `::operator delete(void*, align_val_t)` çağırır veya boyutu `::operator delete(void*, size_t, align_val_t)`silme imza.

**/Zc:alignedYeni** seçenek yalnızca [/std:c++17](std-specify-language-standard-version.md) veya [/std:c++en son](std-specify-language-standard-version.md) etkinleştirildiğinde kullanılabilir. **/std:c++17** veya **/std:c++en son**, **/Zc:alignedNew** varsayılan olarak ISO C++17 standardına uygun olarak etkinleştirilir. Operatör **yeni** ve **silme** uygulamanıztek nedeni aşırı hizalanmış ayırmaları desteklemekse, artık Bu koda C++17 modunda ihtiyacınız olmayabilir. Bu seçeneği kapatmak ve **delete** **/std::c++17** veya **/std:c++latest**, belirt **/Zc:alignedNew-**. **new** İşleç **yeni** uygular ve **sil,** ancak aşırı hizalanmış işleç **yeni** uygulamak ve `align_val_t` parametre var aşırı yükleri **silmek** için hazır değilseniz, derleyici ve Standart Kitaplık aşırı hizalanmış aşırı yüklere çağrı lar üreten önlemek için **/Zc:alignedNew-** seçeneğini kullanın. [/izin verme seçeneği](permissive-standards-conformance.md) **/Zc:alignedNew**varsayılan ayarını değiştirmez.

**/Zc:alignedNew** desteği Visual Studio 2017 sürüm 15.5'ten itibaren kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek, **/Zc:alignedNew** seçeneği ayarlandığında işleç **yeni** ve işleci **silmenin** nasıl bir şekilde nasıl olduğunu gösterir.

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

Bu çıktı 32 bit yapılar için tipiktir. İşaretçi değerleri, uygulamanızın bellekte nerede çalıştığına bağlı olarak değişir.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C++'daki uyumluluk sorunları hakkında bilgi için standart [dışı davranış](../../cpp/nonstandard-behavior.md)konusuna bakın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **C/C++** > **Komut Satırı** özelliği sayfasını seçin.

1. Ek **Seçenekler** özelliğini **/Zc:alignedNew** veya **/Zc:alignedNew-** içerecek şekilde değiştirin ve ardından **Tamam'ı**seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
