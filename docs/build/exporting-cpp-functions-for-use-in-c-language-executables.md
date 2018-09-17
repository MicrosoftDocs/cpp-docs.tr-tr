---
title: C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abdc8dc0f853faf0649581d535cb631c232e8276
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709949"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C Dili Yürütülebilir Öğelerinde Kullanmak için C++ İşlevlerini Dışarı Aktarma

C++ programında yazılan C dili modülünden erişmek istiyorsanız, bu işlevler C++ bağlantısı yerine C bağlaması olan bildirmelidir DLL'de işlevleri varsa. Aksi belirtilmediği sürece, C++ Derleyici C++ tür kullanımı uyumlu (ad düzenlemesi olarak da bilinir) adlandırma ve çağırma kuralları, C'den çağırmak zor olabilecek C++ kullanır.

C bağlaması belirtmek için belirtin `extern "C"` , işlev bildirimleri için. Örneğin:

```
extern "C" __declspec( dllexport ) int MyFunc(long parm1);
```

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](../build/exporting-and-importing-using-afx-ext-class.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [__Declspec(dllimport) kullanarak bir uygulamayı içeri aktarın](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](../build/reference/decorated-names.md)

- [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)