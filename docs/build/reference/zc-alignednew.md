---
title: '/ ZC: alignednew (c ++ 17 aşırı hizalanmış ayırma)'
ms.date: 02/28/2018
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: e0d850d54611579288b81a334af4abdfab6e411c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315806"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/ ZC: alignednew (c ++ 17 aşırı hizalanmış ayırma)

C ++ 17 aşırı hizalanmış desteğini etkinleştirme **yeni**, dinamik bellek ayırma türü için varsayılan en büyük boyutlu standart hizalanmış, büyüktür sınırlarda hizalanmış **max\_hizalama\_t**.

## <a name="syntax"></a>Sözdizimi

> **/ ZC: alignednew**[-]

## <a name="remarks"></a>Açıklamalar

Visual Studio 15.5 sürümünden önceki derleyici ve C ++ 17 Standart aşırı hizalanmış dinamik bellek ayırma için kitaplık desteği sağlar. Zaman **/ZC: alignednew** seçeneği belirtildiğinde, bir dinamik ayırma gibi `new Example;` hizalamasını uyar *örnek* bile büyük olduğunda `max_align_t`, en büyük hizalama herhangi bir temel türü için gereklidir. Ayrılmış türün hizalama olduğunda özgün işleci tarafından sağlanan en fazla **yeni**önceden tanımlanmış makro değeri olarak sunulan  **\_ \_STDCPP\_varsayılan \_Yeni\_hizalama\_\_**, deyim `new Example;` sonuçları bir çağrıda `::operator new(size_t)` C ++ 14 sürümünde yaptığınız gibi. Hizalama olduğunda daha büyük  **\_ \_STDCPP\_varsayılan\_yeni\_hizalama\_\_**, bunun yerine uygulama alır kullanarak bellek `::operator new(size_t, align_val_t)`. Benzer şekilde, aşırı hizalanmış türlere silinmesini çağırır `::operator delete(void*, align_val_t)` veya imza boyutlu silme `::operator delete(void*, size_t, align_val_t)`.

**/ZC: alignednew** seçeneği, yalnızca kullanılabilir olduğunda [/Std: c ++ 17](std-specify-language-standard-version.md) veya [/Std: c ++ Son](std-specify-language-standard-version.md) etkinleştirilir. Altında **/Std: c ++ 17** veya **/Std: c ++ Son**, **/ZC: alignednew** ISO C ++ 17 standardına uygun olması için varsayılan olarak etkindir. Tek nedeni, işleci uygulamak **yeni** ve **Sil** aşırı hizalanmış ayırma desteklemek için artık C ++ 17 modunda bu kodu ihtiyacınız. Bu seçeneği kapatmak ve C ++ 14 davranışı için dönmek için **yeni** ve **Sil** olduğunda **/std::c ++ 17** veya **/Std: c ++ Son** belirtilirse, belirtin **/Zc:alignedNew-**. İşleç uygularsanız **yeni** ve **Sil** ancak aşırı hizalanmış işleci uygulamak hazır olmayan **yeni** ve **Sil** sahip aşırı yüklemeler `align_val_t` parametresi, kullanım **/Zc:alignedNew-** çağrılarını aşırı hizalanmış aşırı yüklemeler için standart kitaplık ve derleyici oluşturmasını önlemek için seçeneği. [/ Permissive-](permissive-standards-conformance.md) seçeneği, varsayılan ayarı değişmez **/ZC: alignednew**.

## <a name="example"></a>Örnek

Bu örnek, gösterir nasıl işleci **yeni** ve işleci **Sil** ne zaman davranır **/ZC: alignednew** seçeneği ayarlanır.

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

Bu çıkış, 32-bit derlemeler için yaygın bir durumdur. Değerler farklı işaretçi, uygulamanızın bellek içinde çalıştığı temel.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: alignednew** veya **/Zc:alignedNew-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
