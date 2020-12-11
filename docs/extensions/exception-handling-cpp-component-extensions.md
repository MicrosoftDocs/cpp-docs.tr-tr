---
description: 'Daha fazla bilgi edinin: özel durum Işleme (C++/CLı ve C++/CX)'
title: Özel Durum İşleme (C++/CLI ve C++/CX)
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
ms.openlocfilehash: 73299cf8b562c3572452e6efd1e8d2fa65aff84c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155065"
---
# <a name="exception-handling--ccli-and-ccx"></a>Özel Durum İşleme (C++/CLI ve C++/CX)

`/ZW`Derleyici seçeneği veya derleyici seçeneği ile derlenen uygulamalar, `/clr` her ikisi de programın yürütülmesi sırasında beklenmeyen hataları işlemek için *özel durumlar* kullanır. Aşağıdaki konular, C++/CX veya C++/CLı uygulamalarında özel durum işlemeyi tartışır.

## <a name="in-this-section"></a>Bu Bölümde

[Yönetilen özel durumları kullanmaya Ilişkin temel kavramlar](../dotnet/basic-concepts-in-using-managed-exceptions.md)<br/>
Özel durumların ve kullanım bloklarının oluşturulmasını açıklar **`try`** / **`catch`** .

[/Clr altında özel durum Işleme davranışındaki farklılıklar](../dotnet/differences-in-exception-handling-behavior-under-clr.md)<br/>
C++ özel durum işlemenin standart davranışından farkları açıklar.

[finally](../dotnet/finally.md)<br/>
Finally anahtar sözcüğünün nasıl kullanılacağını açıklar.

[Nasıl yapılır: genel bir özel durum Işleyicisi tanımlama ve yüklemeyi](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
İşlenmemiş özel durumların nasıl yakalanabileceğini gösterir.

[Nasıl yapılır: MSIL 'den oluşan yerel koddaki özel durumları yakalama](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)<br/>
Yerel koddaki CLR ve C++ özel durumlarının nasıl yakalandığı açıklanmaktadır.

[Nasıl yapılır: genel bir özel durum Işleyicisi tanımlama ve yüklemeyi](../dotnet/how-to-define-and-install-a-global-exception-handler.md)<br/>
İşlenmemiş tüm özel durumların nasıl yakalanacağını gösterir.

## <a name="related-sections"></a>İlgili Bölümler

[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)<br/>
Standart C++ ' da özel durum işlemeyi açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
