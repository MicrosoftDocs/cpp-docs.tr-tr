---
description: 'Hakkında daha fazla bilgi edinin: satır içi işlevleri Içeri ve dışarı aktarma'
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
ms.openlocfilehash: 053280685edf8fa88c969399e7905582534c7493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156196"
---
# <a name="importing-and-exporting-inline-functions"></a>Satır içi işlevleri içeri ve dışarı aktarma

İçeri aktarılan işlevler satır içi olarak tanımlanabilir. Bu efekt kabaca bir standart işlevi satır içi tanımlayarak aynıdır; işlevine yapılan çağrılar, bir makroya benzer şekilde satır içi koda genişletilir. Bu, bir DLL 'de, verimlilik açısından üye işlevlerinin bazılarını satır içi olarak bir, C++ sınıflarını destekleme yöntemi olarak faydalıdır.

İçe aktarılan bir satır işlevinin bir özelliği, adresini C++ ' da götürebilmeniz olur. Derleyici, DLL 'de bulunan satır içi işlevin kopyasının adresini döndürür. İçeri aktarılan satır içi işlevlerin başka bir özelliği de içeri aktarılan işlevin statik yerel verilerini, genel içeri aktarılan verilerden farklı şekilde başlatabilmeniz olabilir.

> [!CAUTION]
> Sürüm çakışmaları olasılığını oluşturabileceğinden içeri aktarılan satır içi işlevleri sağlarken dikkatli olmanız gerekir. Satır içi işlev uygulama koduna genişletilir; Bu nedenle, daha sonra işlevi yeniden verirseniz, uygulamanın kendisi yeniden derlenmediği takdirde bu, güncellenmez. (Normalde, DLL işlevleri onları kullanan uygulamaları yeniden oluşturmadan güncellenebilir.)

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [DLL 'den dışarı aktarma](exporting-from-a-dll.md)

- [Kullanarak DLL 'den dışarı aktarın. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve dışarı aktarma](importing-and-exporting.md)
