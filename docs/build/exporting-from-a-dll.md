---
title: DLL'den dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1beb36b76c54c585505f4d92b33a275e063318e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707986"
---
# <a name="exporting-from-a-dll"></a>DLL'den Dışarı Aktarma

Bir DLL dosyası önemli bir fark dışında bir .exe dosyası çok benzer bir düzeni vardır — bir dışarı aktarma tablosu bir DLL dosyası içerir. Dışarı aktarma tablosu diğer yürütülebilir dosyalar için DLL dışarı aktarmaları her işlevin adını içerir. Bu işlevler, DLL içine için giriş noktalarıdır; işlevleri dışarı aktarma tablosuna yalnızca diğer yürütülebilir dosyaları tarafından erişilebilir. DLL'ye DLL'deki diğer işlevleri özeldir. Kullanarak DLL'den dışarı aktarma tablosu görüntülenebilir [DUMPBIN ](../build/reference/dumpbin-reference.md) /EXPORTS seçeneğiyle aracı.

İki yöntemi kullanarak DLL'den işlevleri dışarı aktarabilirsiniz:

- Modül tanım (.def) dosyası oluşturun ve DLL'yi oluştururken .def dosyasını kullanın. İsterseniz, bu yaklaşımı kullanın [tarafından ad yerine sıraya işlevlerini kullanarak DLL'den dışa aktarma](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

- Anahtar sözcüğünü kullanın **__declspec(dllexport)** işlevin tanımı.

İki yöntemden biriyle işlevleri dışa aktarırken kullandığınızdan emin olun [__stdcall](../cpp/stdcall.md) çağırma kuralı.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [.Def dosyalarını kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak içeri ve dışarı aktarma](../build/exporting-and-importing-using-afx-ext-class.md)

- [C dili çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ dili çalıştırılabilirlerinde kullanmak için C işlevlerini dışa aktarma](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [İşlevler tarafından ad yerine sıraya DLL'den dışarı aktarma](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)

- [Hangi dışa aktarma yönteminin kullanılacağını belirleme](../build/determining-which-exporting-method-to-use.md)

- [Hangi bağlama yönteminin kullanılacağını belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Bir uygulamaya aktarma](../build/importing-into-an-application.md)

- [İçeri ve dışarı aktarma satır içi işlevler](../build/importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](../build/mutual-imports.md)

## <a name="see-also"></a>Ayrıca Bkz.

[İçeri ve Dışarı Aktarma](../build/importing-and-exporting.md)