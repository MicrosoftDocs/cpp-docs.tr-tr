---
title: Satır içi işlevleri içeri ve dışarı aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
ms.openlocfilehash: abb0443ab8fbd315524350caaff34e0250147ed2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328510"
---
# <a name="importing-and-exporting-inline-functions"></a>Satır içi işlevleri içeri ve dışarı aktarma

İçe aktarılan işlevler satır içinde olarak tanımlanabilir. Etkisi kabaca standart bir işlev satırlı tanımlayan aynıdır; işlevine yapılan çağrılar, makro gibi satır içinde koda genişletilir. Bu, temel olarak, c++ sınıflarını verimlilik için bazı üye işlevlerini hizalayan bir DLL'de desteklemenin bir yolu olarak yararlıdır.

İçe aktarılan satır lı işlevin bir özelliği, c++'da adresini alabiliyor olabilirsiniz. Derleyici, DLL'de bulunan satır içinde işlev inline işlevinin kopyasının adresini döndürür. İçe aktarılan satır İçi işlevlerin bir diğer özelliği de, genel içe aktarılan verilerin aksine, içe aktarılan işlevin statik yerel verilerini başlatmanızdır.

> [!CAUTION]
> Sürüm çakışmaları olasılığını oluşturabildiklerinden, içe aktarılan satır İçi işlevleri sağlarken dikkatli olmalısınız. Satır dışı bir işlev uygulama koduna genişletilir; bu nedenle, daha sonra işlevi yeniden yazarsanız, uygulamanın kendisi yeniden derlenmedikçe güncelleştirilmez. (Normalde, DLL işlevleri bunları kullanan uygulamaları yeniden oluşturmadan güncellenebilir.)

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir DLL'den dışa aktarma](exporting-from-a-dll.md)

- [Kullanarak bir DLL'den dışa aktarma. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) kullanarak bir DLL'den dışa aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak ihracat ve ithalat](exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilir cihazlarda kullanılmak üzere C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)
