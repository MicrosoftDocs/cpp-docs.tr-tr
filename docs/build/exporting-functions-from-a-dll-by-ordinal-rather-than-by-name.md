---
title: DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma
ms.date: 11/04/2016
f1_keywords:
- NONAME
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: 6a5ac13fdc85b3cb1626aefa28b92866a8c856c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503423"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma

En basit yolu, bir DLL'den işlevleri dışarı aktarmak için bunları adına göre dışa aktarılmamasıdır. Bu kullandığınızda neler olduğunu **__declspec(dllexport)**, örneğin. Ancak, bunun yerine sıralı olarak işlevleri dışarı aktarabilirsiniz. Bu teknikte bir .def dosyası yerine kullanmalısınız **__declspec(dllexport)**. Bir işlevin sıra değeri belirtmek için kendi sıra .def dosyasında işlev adı ekleyin. Sıra sayıları belirtme hakkında daha fazla bilgi için bkz: [.def dosyası kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md).

> [!TIP]
>  DLL dosyanızın boyutunu en iyi duruma getirmek istediğiniz kullanırsanız **NONAME** her dışarı aktarılan işlevin özniteliği. İle **NONAME** özniteliği, sıra sayıları içinde depolanıyorsa tablosu yerine işlev adlarını DLL'nin dışarı aktarma. Birçok işlevleri dışa aktarıyorsanız, bu önemli ölçüde tasarruf olabilir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Sıralı olarak dışarı aktarabilir, dolayısıyla bir .def dosyası kullanmanıza](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanın](../build/exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)