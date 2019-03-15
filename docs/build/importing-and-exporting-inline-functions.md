---
title: İçeri ve dışarı aktarma satır içi işlevler
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
ms.openlocfilehash: ed523d84228124d4a8d99e443c0c744f362f1c56
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822047"
---
# <a name="importing-and-exporting-inline-functions"></a>İçeri ve dışarı aktarma satır içi işlevler

İçeri aktarılan işlevler, satır içi olarak tanımlanabilir. Etkisi kabaca bir standart bir işlevi satır içi tanımlama aynıdır; işlev çağrıları, bir makro benzer bir satır içi kod içine genişletilir. Bu, temelde C++ destekleyen bir yol DLL'de verimlilik için bazı üye işlevleri, sınıflarını kullanışlıdır.

Bir içeri aktarılan satır içi işlev c++'ta adresini alabilir özelliğidir. Derleyici DLL'de yer alan satır içi işlev kopyasını adresini döndürür. Başka bir içeri aktarılan satır içi işlevleri içeri aktarılan işlevinin genel içeri aktarılan verileri farklı olarak statik yerel veriler başlatabilirsiniz özelliğidir.

> [!CAUTION]
>  Sürüm çakışması olasılığı oluşturduğundan sağlama satır içi işlevleri içeri aktarırken dikkatli olmanız. Satır içi işlev, uygulama kodunda genişletilmiş; Daha sonra işlevi yeniden yazma, uygulamanın kendisi yeniden derlenen sürece bu nedenle, bu güncelleştirilmiyor. (Normalde, DLL işlevleri bunları kullanan uygulamalar yeniden derlenmeden güncelleştirilebilir.)

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [DLL'den dışarı aktarma](exporting-from-a-dll.md)

- [Kullanarak bir DLL dışarı aktarın. DEF dosyaları](exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)
