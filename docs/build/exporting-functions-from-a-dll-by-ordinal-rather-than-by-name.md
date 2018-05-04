---
title: İşlevleri dışarı aktarma DLL'den yerine sıraya göre adı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- NONAME
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b05f3e429406b3c24c7a21ce9ee8e10fe19c14b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma
Ada göre verilecek en basit yolu, DLL'den dışarı aktarma işlevleri var. Bu kullandığınızda neler olduğunu **__declspec(dllexport)**, örneğin. Ancak, bunun yerine işlevleri sıralı olarak dışa aktarabilirsiniz. Bu teknikle .def dosyası yerine kullanmalısınız **__declspec(dllexport)**. Bir işlevin sıra sayısı değerini belirtmek için kendi sıra .def dosyası işlev adı ekleyin. Sıra numaraları belirtme hakkında daha fazla bilgi için bkz: [.def dosyaları kullanarak DLL'den dışarı aktarma](../build/exporting-from-a-dll-using-def-files.md).  
  
> [!TIP]
>  DLL dosyası boyutu en iyi hale getirmek istiyorsanız, kullanmak **NONAME** dışarı aktarılan her işlevi özniteliği. İle **NONAME** özniteliği, sıra numaraları depolanır işlev adları yerine tablo DLL dışarı aktarma. Birçok işlevini veriyorsanız bu önemli tasarruf olabilir.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
-   [Sıralı olarak dışa aktarabilirsiniz şekilde .def dosyası kullanın](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec(dllexport) kullanın](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL'den Dışarı Aktarma](../build/exporting-from-a-dll.md)