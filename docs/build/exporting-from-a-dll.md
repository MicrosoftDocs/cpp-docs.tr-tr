---
description: "Hakkında daha fazla bilgi edinin: DLL 'den dışarı aktarma"
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
ms.openlocfilehash: 324ca733eab48973dc9ca902f81abfe4ce52a5c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162943"
---
# <a name="exporting-from-a-dll"></a>DLL'den Dışarı Aktarma

Bir DLL dosyası bir. exe dosyasına benzer bir şekilde, önemli bir farklılık içeren bir düzen içerir. bir DLL dosyası dışarı aktarmalar tablosu içerir. Dışarı aktarmalar tablosu, DLL 'nin diğer yürütülebilir dosyalara aktardığı her işlevin adını içerir. Bu işlevler DLL 'deki giriş noktalarıdır; diğer yürütülebilir dosyalar yalnızca dışarı aktarmalar tablosundaki işlevlere erişebilir. DLL 'deki diğer işlevler DLL 'ye özeldir. DLL 'nin dışarı aktarmalar tablosu, [dumpbin](reference/dumpbin-reference.md) Aracı kullanılarak/dışarı aktarmalar seçeneğiyle görüntülenebilir.

İki yöntemi kullanarak bir DLL 'den işlevleri dışa aktarabilirsiniz:

- DLL oluştururken bir modül tanımı (. def) dosyası oluşturun ve. def dosyasını kullanın. [DLL 'inizdeki işlevleri ad yerine sıraya göre dışarı aktarmak](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)istiyorsanız bu yaklaşımı kullanın.

- İşlevin tanımındaki anahtar sözcüğünü kullanın **`__declspec(dllexport)`** .

İki yöntemden birini kullanarak işlevleri dışarı aktarırken [__stdcall](../cpp/stdcall.md) çağırma kuralını kullandığınızdan emin olun.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [. Def dosyalarını kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS kullanarak dışarı ve içeri aktarma](exporting-and-importing-using-afx-ext-class.md)

- [C Dili Çalıştırılabilirlerinde kullanmak için C++ işlevlerini dışa aktarma](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C veya C++ Dili Çalıştırılabilirlerinde kullanmak için C işlevlerini dışarı aktarma](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [DLL 'den işlevleri ad yerine sıraya göre dışarı aktarma](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)

- [Hangi dışarı aktarma yönteminin kullanılacağını belirleme](determining-which-exporting-method-to-use.md)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

- [DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Bir uygulamaya aktarma](importing-into-an-application.md)

- [Satır içi işlevleri içeri ve dışarı aktarma](importing-and-exporting-inline-functions.md)

- [Karşılıklı içeri aktarmalar](mutual-imports.md)

## <a name="see-also"></a>Ayrıca bkz.

[İçeri ve dışarı aktarma](importing-and-exporting.md)
