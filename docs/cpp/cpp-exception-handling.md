---
title: C++ Özel Durum İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
ms.openlocfilehash: b4eaab7d5bb352cccc612dd950572464b82b67e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392316"
---
# <a name="c-exception-handling"></a>C++ Özel Durum İşleme

C++ dili özel durum oluşturmak ve yakalamak için yerleşik destek sağlar. C++'ta programlarken, yerleşik C++ özel durum desteğini hemen hemen her zaman bu bölümde açıklandığı gibi kullanmalısınız.

C++ özel durum işleme kodunuzda etkinleştirmek için [/ehsc](../build/reference/eh-exception-handling-model.md).

## <a name="in-this-section"></a>Bu Bölümde

C++ özel durum işlemesi hakkındaki bu tartışma şunları içerir:

- [Try, catch ve throw deyimleri](../cpp/try-throw-and-catch-statements-cpp.md)

- [Yakala Bloğu Nasıl Değerlendirilir](../cpp/how-catch-blocks-are-evaluated-cpp.md)

- [Özel durumlar ve yığını geriye doğru izleme](../cpp/exceptions-and-stack-unwinding-in-cpp.md)

- [Özel durum belirtimleri](../cpp/exception-specifications-throw-cpp.md)

- [noexcept](../cpp/noexcept-cpp.md)

- [İşlenilmeyen C++ Özel Durumları](../cpp/unhandled-cpp-exceptions.md)

- [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)

## <a name="support-for-earlier-mfc-exceptions"></a>Önceki MFC Özel Durumları için Destek

Sürüm 4.0 itibariyle, MFC, C++ özel durum işleme mekanizmasını kullanarak başladı. C++ özel durum işlemeyi yeni kod içinde kullanmanız teşvik edilse de, MFC sürüm 4.0 ve sonraki sürümler önceki sürümlerdeki MFC makroları korur, böylece eski kodlar bozulmaz. Makrolar ile yeni bir mekanizma da birleştirilebilir. Makrolar karıştırma hakkında bilgi ve C++ makaleleri yeni mekanizmasını kullanmak üzere özel durum işleme ve eski dönüştürmeyle ilgili kod [özel durumlar: MFC makrolarını kullanma ve C++ özel durumları](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) ve [özel durumlar: MFC özel durum makrolarından dönüştürme](../mfc/exceptions-converting-from-mfc-exception-macros.md). Eski MFC özel durum makrolarını hala kullanmaya devam ediyorsanız, C++ özel durum anahtar sözcüklerini değerlendirin. Bkz: [özel durumlar: Sürüm 3. 0'da özel durum makrolarındaki değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)