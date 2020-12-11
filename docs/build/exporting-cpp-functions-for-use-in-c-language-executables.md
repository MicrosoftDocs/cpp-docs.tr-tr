---
description: 'Hakkında daha fazla bilgi edinin: C Dili Çalıştırılabilirlerinde kullanmak için C++ Işlevlerini dışa aktarma'
title: C Dili Yürütülebilir Öğelerinde Kullanmak için C++ İşlevlerini Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
ms.openlocfilehash: c11ee56afb6fc99dbdf5a795cb8551e54835cd67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156625"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C Dili Yürütülebilir Öğelerinde Kullanmak için C++ İşlevlerini Dışarı Aktarma

C dili modülünden erişmek istediğiniz C++ dilinde yazılmış bir DLL 'de işlevleriniz varsa, bu işlevleri C++ bağlantısı yerine C bağlantısıyla bildirmelisiniz. Aksi belirtilmediği sürece, C++ derleyicisi C++ türü güvenli adlandırma (ad dekorasyonu olarak da bilinir) ve C++ çağırma kurallarını kullanır ve bu da C 'den çağrı yapmak zor olabilir.

C bağlantısı belirtmek için, `extern "C"` işlev bildirimleriniz için belirtin. Örneğin:

```
extern "C" __declspec( dllexport ) int MyFunc(long parm1);
```

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [. Def dosyalarını kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C veya C++ Dili Çalıştırılabilirlerinde kullanmak için C işlevlerini dışarı aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](reference/decorated-names.md)

- [Bağlantıyı Belirtmek için extern Kullanma](../cpp/extern-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
