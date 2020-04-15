---
title: MSVC'de özel durum işleme
description: C++ dil referans özel durum işleme genel bakış.
ms.date: 04/15/2020
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 0d60f49c6f1412925c19aaf497352940411b5d92
ms.sourcegitcommit: 0e4feb35b47c507947262d00349d4a893863a6d3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81396283"
---
# <a name="exception-handling-in-msvc"></a>MSVC'de özel durum işleme

Özel durum, programın normal yürütme yolu boyunca devam etmesini engelleyen bir hata koşuludur, büyük olasılıkla programın denetimi dışındadır. Nesne oluşturma, dosya girişi/çıktısı ve diğer modüllerden yapılan işlev çağrıları da dahil olmak üzere belirli işlemler, programınız doğru çalışıyor olsa bile tüm olası özel durumlar kaynaklarıdır. Sağlam kod, özel durumları tahmin eder ve işler. Mantık hatalarını algılamak için, özel durumlar yerine iddiaları kullanın [(bkz.](/visualstudio/debugger/c-cpp-assertions)

## <a name="kinds-of-exceptions"></a>İstisna türleri

Microsoft C++ derleyicisi (MSVC) üç tür özel durum işlemeyi destekler:

- [C++ özel durum işleme](errors-and-exception-handling-modern-cpp.md)

   Çoğu C++ programı için C++ özel durum işlemeyi kullanmalısınız. Tür güvenlidir ve yığın boşaltma sırasında nesne yıkıcıların çağrılmasını sağlar.

- [Yapılandırılmış özel durum işleme](structured-exception-handling-c-cpp.md)

   Windows, yapılandırılmış özel durum işleme (SEH) adı verilen kendi özel durum mekanizmasını sağlar. C++ veya MFC programlaması için önerilmez. SEH'yi yalnızca MFC Olmayan Programlarda kullanın.

- [MFC özel durumları](../mfc/exception-handling-in-mfc.md)

   Sürüm 3.0'dan beri, MFC C++ özel durumlarını kullanmıştır. Yine de formdaki C++ özel durumlarına benzeyen eski özel durum işleme makrolarını destekler. MFC makroları ve C++ özel durumlarını karıştırma hakkında tavsiye için [bkz.](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

C++ projesinde kullanılacak özel durum işleme modelini belirtmek için [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanın. Standart C++ özel durum işleme (**/EHsc**) Visual Studio'daki yeni C++ projelerinde varsayılan değerdir.

Özel durum işleme mekanizmalarını karıştırmanızı önermiyoruz. Örneğin, yapılandırılmış özel durum işleme ile C++ özel durumları kullanmayın. C++ özel durum işlemeyi kullanmak yalnızca kodunuzu daha taşınabilir hale getirir ve her türlü özel durumları işlemenizi sağlar. Yapılandırılmış özel durum işlemenin dezavantajları hakkında daha fazla bilgi için [bkz.](structured-exception-handling-c-cpp.md)

## <a name="in-this-section"></a>Bu bölümde

- [Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)

- [Özel durum güvenliğine yönelik tasarım](how-to-design-for-exception-safety.md)

- [İstisnai ve istisnai olmayan kod lar arasında nasıl arayüz oluşur?](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [İfadeleri deneyin, yakalayın ve atın](try-throw-and-catch-statements-cpp.md)

- [Yakala Bloğu Nasıl Değerlendirilir](how-catch-blocks-are-evaluated-cpp.md)

- [Özel Durumlar ve Yığın Gevşeme](exceptions-and-stack-unwinding-in-cpp.md)

- [Özel Durum Özellikleri](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [İşlenilmeyen C++ Özel Durumları](unhandled-cpp-exceptions.md)

- [Karıştırma C (Yapılandırılmış) ve C++ Özel Durumları](mixing-c-structured-and-cpp-exceptions.md)

- [Yapılandırılmış özel durum işleme (SEH) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](cpp-language-reference.md)</br>
[x64 özel durum işleme](../build/exception-handling-x64.md)</br>
[Özel Durum Taşıma (C++/CLI ve C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
