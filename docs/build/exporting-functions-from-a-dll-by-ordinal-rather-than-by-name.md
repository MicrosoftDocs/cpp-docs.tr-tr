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
ms.openlocfilehash: fe34ec90aa775e7435d4a02b9d77a9cb9c8fdd65
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423306"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma

En basit yolu, bir DLL'den işlevleri dışarı aktarmak için bunları adına göre dışa aktarılmamasıdır. Bu kullandığınızda neler olduğunu **__declspec(dllexport)**, örneğin. Ancak, bunun yerine sıralı olarak işlevleri dışarı aktarabilirsiniz. Bu teknikte bir .def dosyası yerine kullanmalısınız **__declspec(dllexport)**. Bir işlevin sıra değeri belirtmek için kendi sıra .def dosyasında işlev adı ekleyin. Sıra sayıları belirtme hakkında daha fazla bilgi için bkz: [.def dosyası kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md).

> [!TIP]
>  DLL dosyanızın boyutunu en iyi duruma getirmek istediğiniz kullanırsanız **NONAME** her dışarı aktarılan işlevin özniteliği. İle **NONAME** özniteliği, sıra sayıları içinde depolanıyorsa tablosu yerine işlev adlarını DLL'nin dışarı aktarma. Birçok işlevleri dışa aktarıyorsanız, bu önemli ölçüde tasarruf olabilir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Sıralı olarak dışarı aktarabilir, dolayısıyla bir .def dosyası kullanmanıza](../build/exporting-from-a-dll-using-def-files.md)

- [__Declspec(dllexport) kullanın](../build/exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)
