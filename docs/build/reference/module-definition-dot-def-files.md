---
title: Modül tanımı (. Def) dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57bad3a63e910918b6a22b6263f0df3faca0dcd1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="module-definition-def-files"></a>Modül-Tanımlama (.Def) Dosyaları
Modül-tanımlama (.def) dosyaları bağlayıcı dışarı aktarma, öznitelikler ve diğer bilgileri bağlanması programı hakkında bilgiler sağlar. .Def dosyası DLL oluştururken kullanışlıdır. Olduğundan [bağlayıcı seçenekleri](../../build/reference/linker-options.md) kullanılabilecek modül tanımlama deyimleri yerine .def dosyaları genellikle gerekli değildir. Aynı zamanda [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) belirtmek için bir yol işlevleri verdi.  
  
 İle bağlayıcı aşamasında .def dosyası çağırabileceği [/def (modül tanım dosyasını belirtin)](../../build/reference/def-specify-module-definition-file.md) bağlayıcı seçeneği.  
  
 .Def dosyası kullanarak, hiçbir dışarı aktarma içeren bir .exe dosyası oluşturuluyorsa, çıktı dosyası daha büyük ve daha yavaş yükleniyor hale getirir.  
  
 Bir örnek için bkz: [bir DLL kullanarak DEF dosyaları dışarı aktarma](../../build/exporting-from-a-dll-using-def-files.md).  
  
 Daha fazla bilgi edinmek için aşağıdaki bölümlere bakın:  
  
-   [Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTS](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [LIBRARY](../../build/reference/library.md)  
  
-   [ADI](../../build/reference/name-c-cpp.md)  
  
-   [BÖLÜMLER](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [SÜRÜM](../../build/reference/version-c-cpp.md)  
  
-   [Ayrılmış sözcükler](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  