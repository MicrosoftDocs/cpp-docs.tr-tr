---
title: Visual C++'da Özel Durum İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: a155d56cc234c11534f5456ef92ea913e094f1a8
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627286"
---
# <a name="exception-handling-in-visual-c"></a>Visual C++'da Özel Durum İşleme

Bir özel durum denetimi dışında kalan programın normal yürütme yolu devam etmesini engelleyen büyük olasılıkla programın, bir hata durumudur. Hatta programınızı doğru çalışırken nesne oluşturma, dosya giriş/çıkış ve diğer modüllerden yapılan işlev çağrılarının da dahil olmak üzere belirli, özel durumların tüm olası kaynakları işlemlerdir. Güçlü kod düşünmektedir ve özel durumları işler.

Tek bir program veya Modül içindeki mantık hataları algılamak için özel durumlar yerine onaylar kullanın (bkz [kullanarak Onaylamalar](/visualstudio/debugger/c-cpp-assertions)).

Visual C++ üç özel durum işleme türünü destekler:

- [C++ özel durum işleme](../cpp/cpp-exception-handling.md)

   C++ programları için hangi tür bakımından güvenlidir ve yığın geriye doğru izleme sırasında yok edicinin çağrılmadığına söz konusu nesne sağlar, C++ özel durum işleme kullanmanız gerekir.

- [Yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md)

   Windows SEH adı verilen kendi özel durum mekanizması sağlar. C++ ya da MFC programlama için önerilmez. SEH yalnızca MFC olmayan C programlarında kullanın.

- [MFC özel durumları](../mfc/exception-handling-in-mfc.md)

   Sürüm 3.0, bu yana MFC C++ özel durumlarını kullanılmış, ancak yine de C++ özel durumlarını formunda benzer makroları, işleme, eski özel durumu destekler. Bu makrolar için yeni programlama önerilmez olsa da, bunlar yine de geriye dönük uyumluluk için desteklenir. Makroları kullanan programlar içinde de C++ özel durumlarını ücretsiz olarak kullanabilirsiniz. Ön işleme sırasında özel durum işleme Visual C++ uygulaması C++ dili Visual C++ sürüm 2. 0'den itibaren tanımlı anahtar sözcükler için makroları değerlendirir. C++ özel durumlarını kullanmayı başlatırken mevcut bir özel durum makroları yerinde bırakabilirsiniz.

Kullanma [/EH](../build/reference/eh-exception-handling-model.md) bir projede; kullanmak için özel durum işleme türünü belirtmek için derleyici seçeneği C++ özel durum işleme varsayılandır. Hata işleme düzenekleri karıştırmayın; Örneğin, C++ özel durumlarını, yapılandırılmış özel durum işleme ile kullanmayın. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir yapar ve herhangi bir türde özel durumları işlemenizi sağlar. Yapılandırılmış özel durum işleme dezavantajları hakkında daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). MFC makroları ve C++ özel durumlarını karıştırma hakkında daha fazla öneri için bkz. [özel durumlar: MFC makroları ve C++ özel durumlarını kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

CLR uygulamaları özel durumları işleme hakkında daha fazla bilgi için bkz: [özel durum işleme (C + +/ CLI ve C + +/ CX)](../windows/exception-handling-cpp-component-extensions.md).

Özel durum x64 üzerinde işleme hakkında bilgi için işlemciler bkz [x64 özel durum işleme](../build/exception-handling-x64.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)