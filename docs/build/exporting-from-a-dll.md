---
title: DLL'den Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
ms.openlocfilehash: 6bdf5b86724ae07aa073a9feb1cc4d5723bc6e6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196748"
---
# <a name="exporting-from-a-dll"></a>DLL'den Dışarı Aktarma

Bir DLL dosyası önemli bir fark dışında bir .exe dosyası çok benzer bir düzeni vardır — bir dışarı aktarma tablosu bir DLL dosyası içerir. Dışarı aktarma tablosu diğer yürütülebilir dosyalar için DLL dışarı aktarmaları her işlevin adını içerir. Bu işlevler, DLL içine için giriş noktalarıdır; işlevleri dışarı aktarma tablosuna yalnızca diğer yürütülebilir dosyaları tarafından erişilebilir. DLL'ye DLL'deki diğer işlevleri özeldir. Kullanarak DLL'den dışarı aktarma tablosu görüntülenebilir [DUMPBIN ](reference/dumpbin-reference.md) /EXPORTS seçeneğiyle aracı.

İki yöntemi kullanarak DLL'den işlevleri dışarı aktarabilirsiniz:

- Modül tanım (.def) dosyası oluşturun ve DLL'yi oluştururken .def dosyasını kullanın. İsterseniz, bu yaklaşımı kullanın [tarafından ad yerine sıraya işlevlerini kullanarak DLL'den dışa aktarma](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

- Anahtar sözcüğünü kullanın **__declspec(dllexport)** işlevin tanımı.

İki yöntemden biriyle işlevleri dışa aktarırken kullandığınızdan emin olun [__stdcall](../cpp/stdcall.md) çağırma kuralı.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [İşlevler tarafından ad yerine sıraya DLL'den dışarı aktarma](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

- [DLL'yi Başlat](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Bir uygulamaya aktarma](importing-into-an-application.md)

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)
