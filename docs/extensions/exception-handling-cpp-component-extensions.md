---
title: Özel durum IşlemeC++(/CLI C++ve/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- structured exception handling [C++], managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
ms.openlocfilehash: 9f5662bb9e744b5db3b0ab25ac4230b2f67016bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182129"
---
# <a name="exception-handling--ccli-and-ccx"></a>Özel durum IşlemeC++(/CLI C++ve/CX)

`/ZW` derleyici seçeneği veya `/clr` derleyici seçeneği ile derlenen uygulamalar, her ikisi de programın yürütülmesi sırasında beklenmeyen hataları işlemek için *özel durumlar* kullanır. Aşağıdaki konular, C++/CX veya C++/CLI uygulamalarında özel durum işlemeyi tartışır.

## <a name="in-this-section"></a>Bu Bölümde

[Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
Özel durumların üretilmesini ve **try**/**catch** bloklarını kullanmayı açıklar.

[/Clr altında özel durum Işleme davranışındaki farklılıklar](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
C++ Özel durum işlemenin standart davranışından farkları açıklar.

[finally](../dotnet/finally.md)<br/>
Finally anahtar sözcüğünün nasıl kullanılacağını açıklar.

[Nasıl yapılır: Genel Bir Özel Durum İşleyicisi Tanımlama ve Yükleme](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
İşlenmemiş özel durumların nasıl yakalanabileceğini gösterir.

[Nasıl yapılır: MSIL'den Oluşan Yerel Kodda Catch Özel Durumları](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
Yerel koddaki CLR ve C++ özel durumların nasıl yakalandığı açıklanmaktadır.

[Nasıl yapılır: Genel Bir Özel Durum İşleyicisi Tanımlama ve Yükleme](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
İşlenmemiş tüm özel durumların nasıl yakalanacağını gösterir.

## <a name="related-sections"></a>İlgili Bölümler

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
Standart C++olarak özel durum işlemeyi açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
