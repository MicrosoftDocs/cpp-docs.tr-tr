---
title: C Dili Yürütülebilir Öğelerinde Kullanmak için C++ İşlevlerini Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
ms.openlocfilehash: a694b77e3730ab82ec1698076cc66729ff115cdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195240"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>C Dili Yürütülebilir Öğelerinde Kullanmak için C++ İşlevlerini Dışarı Aktarma

C++ programında yazılan C dili modülünden erişmek istiyorsanız, bu işlevler C++ bağlantısı yerine C bağlaması olan bildirmelidir DLL'de işlevleri varsa. Aksi belirtilmediği sürece, C++ Derleyici C++ tür kullanımı uyumlu (ad düzenlemesi olarak da bilinir) adlandırma ve çağırma kuralları, C'den çağırmak zor olabilecek C++ kullanır.

C bağlaması belirtmek için belirtin `extern "C"` , işlev bildirimleri için. Örneğin:

```
extern "C" __declspec( dllexport ) int MyFunc(long parm1);
```

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) kullanarak bir uygulamaya aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL'yi Başlat](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Düzenlenmiş adlar](reference/decorated-names.md)

- [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
