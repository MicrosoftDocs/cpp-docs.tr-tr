---
title: MSVC 'de özel durum işleme
ms.date: 11/19/2019
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 6cf71d6e6d0519951a084ebead65003bd363395f
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246585"
---
# <a name="exception-handling-in-msvc"></a>MSVC 'de özel durum işleme

Özel durum muhtemelen programın denetimi dışında, programın normal yürütme yolunda devam etmesini önleyen bir hata durumudur. Nesne oluşturma, dosya girişi/çıktısı ve diğer modüllerden yapılan işlev çağrıları dahil bazı işlemler, programınız doğru şekilde çalıştığında bile tüm olası özel durum kaynaklarıdır. Sağlam kod anticipates ve özel durumları işler. Mantık hatalarını saptamak için özel durumlar yerine onayları kullanın (bkz. [onayları kullanma](/visualstudio/debugger/c-cpp-assertions)).

## <a name="kinds-of-exceptions"></a>Özel durum türleri

Microsoft C++ DERLEYICISI (MSVC) üç tür özel durum işlemeyi destekler:

- [C++özel durum işleme](errors-and-exception-handling-modern-cpp.md)

   Çoğu C++ program için, tür kullanımı güvenli C++ olan özel durum işleme kullanmanız gerekir ve yığın geri sarma sırasında nesne yıkıcılarının çağrılmasını sağlar.

- [Yapılandırılmış özel durum işleme](structured-exception-handling-c-cpp.md)

   Windows, SEH adlı kendi özel durum mekanizmasını sağlar. Ya da MFC programlama için C++ önerilmez. SEH yalnızca MFC olmayan C programlarında kullanın.

- [MFC özel durumları](../mfc/exception-handling-in-mfc.md)

Bir projede kullanılacak özel durum işlemenin türünü belirtmek için [/Eh](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanın; C++ özel durum işleme varsayılandır. Hata işleme mekanizmalarını karıştırmayın; Örneğin, yapılandırılmış özel durum işleme C++ ile özel durumlar kullanmayın. Özel C++ durum işlemenin kullanılması, kodunuzun daha taşınabilir olmasını sağlar ve herhangi bir türdeki özel durumları idare etmenizi sağlar. Yapılandırılmış özel durum işlemenin dezavantajları hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](structured-exception-handling-c-cpp.md). MFC makrolarını ve C++ özel durumlarını karıştırma hakkında öneri için bkz. [özel durumlar: MFC makrolarını C++ ve özel durumlarını kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="in-this-section"></a>Bu bölümde

- [Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](errors-and-exception-handling-modern-cpp.md)

- [Özel durum güvenliği için tasarım](how-to-design-for-exception-safety.md)

- [Olağanüstü ve olağanüstü olmayan kod arasında arabirim oluşturma](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [TRY, catch ve throw deyimleri](try-throw-and-catch-statements-cpp.md)

- [Yakala Bloğu Nasıl Değerlendirilir](how-catch-blocks-are-evaluated-cpp.md)

- [Özel durumlar ve yığın geri sarma](exceptions-and-stack-unwinding-in-cpp.md)

- [Özel durum belirtimleri](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [İşlenilmeyen C++ Özel Durumları](unhandled-cpp-exceptions.md)

- [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](mixing-c-structured-and-cpp-exceptions.md)

- [Yapılandırılmış özel durum Işleme (SEH) (CC++/)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](cpp-language-reference.md)</br>
[x64 özel durum işleme](../build/exception-handling-x64.md)</br>
[Özel durum IşlemeC++(/CLI C++ve/CX)](../extensions/exception-handling-cpp-component-extensions.md)
