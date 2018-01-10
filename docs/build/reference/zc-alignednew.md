---
title: "/ZC:alignedNew (c ++ 17 aşırı hizalanmış ayırma) | Microsoft Docs"
ms.date: 12/14/2017
ms.technology: cpp-tools
ms.topic: article
f1_keywords: /Zc:alignedNew
dev_langs: C++
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a4d6e801b258697154a4b11c7b5e468c090cc94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/ZC:alignedNew (c ++ 17 aşırı hizalanmış ayırma)

Aşırı hizalı C ++ 17 desteğini etkinleştirme **yeni**, dinamik bellek ayırma türü için varsayılan en büyük ölçekli standart hizalanmış, büyük sınırlarındaki hizalı **max\_Hizala\_t**.

## <a name="syntax"></a>Sözdizimi

> **/ZC:alignedNew**[-]

## <a name="remarks"></a>Açıklamalar

Visual Studio sürüm 15,5 derleyici ve C ++ 17 Standart aşırı hizalanmış dinamik bellek ayırma için kitaplık desteği sağlar. Zaman **/Zc:alignedNew** seçeneği belirtildiğinde, dinamik ayırma gibi `new Example;` hizalamasını uyar *örnek* bile, büyük olduğunda `max_align_t`, en büyük hizalama herhangi bir temel türü için gereklidir. Ayrılmış türü hizalamasını olduğunda, özgün işleciyle garanti en fazla **yeni**, önceden tanımlanmış makrosu değeri olarak kullanılabilir  **\_ \_STDCPP\_varsayılan \_Yeni\_hizalama\_\_**, deyim `new Example;` yapılan bir çağrı sonuçlanıyor `::operator new(size_t)` C ++ 14'te yaptığınız gibi. Hizalama olduğunda büyük  **\_ \_STDCPP\_varsayılan\_yeni\_hizalama\_\_**, bunun yerine uygulama alır kullanarak bellek `::operator new(size_t, align_val_t)`. Benzer şekilde, aşırı hizalanmış türleri silinmesini çağırır `::operator delete(void*, align_val_t)` veya boyutlu imzayı silme `::operator delete(void*, size_t, align_val_t)`.

**/Zc:alignedNew** seçenek, yalnızca kullanılabilir olduğunda [/Std: c ++ 17](std-specify-language-standard-version.md) veya [/Std: c ++ Son](std-specify-language-standard-version.md) etkinleştirilir. Altında **/Std: c ++ 17** veya **/Std: c ++ Son**, **/Zc:alignedNew** C ++ 17 standart ISO için uygun olması için varsayılan olarak etkindir. Yalnızca neden olursa işleci uygulamak **yeni** ve **silmek** aşırı hizalanmış ayırmaları desteklemektir artık bu kodu C ++ 17 modunda gerekebilir. Bu seçeneği kapatmak ve C ++ 14 davranışını için geri döndürmek için **yeni** ve **silmek** zaman **/std::c ++ 17** veya **/Std: c ++ Son** belirtilirse, belirtin **/Zc:alignedNew-**. İşleç uygularsanız **yeni** ve **silmek** ancak aşırı hizalanmış işleci uygulamak hazır olmayan **yeni** ve **silme** sahip aşırı `align_val_t` parametresi, kullanım **/Zc:alignedNew-** derleyicisi ve standart kitaplığı oluşturulmasını önlemek için seçeneği aşırı hizalanmış aşırı çağırır.

## <a name="example"></a>Örnek

Bu örnek göstermektedir nasıl işleci **yeni** and işleci **silmek** ne zaman davranır **/Zc:alignedNew** seçeneği ayarlanmış.

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

Bu çıktı, 32-bit derlemeler için genel bir durumdur. Değerler farklı işaretçi uygulamanızı bellekte çalıştığı temel.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **komut satırı** özellik sayfasında **C/C++** klasör.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:alignedNew** veya **/Zc:alignedNew-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)  
