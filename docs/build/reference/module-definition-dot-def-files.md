---
title: "Modül tanımı (. Def) dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15dbdfcd1074b32e2a707616571484db3ced9d2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="module-definition-def-files"></a>Modül-Tanımlama (.Def) Dosyaları
Modül-tanımlama (.def) dosyaları bağlayıcı dışarı aktarma, öznitelikler ve diğer bilgileri bağlanması programı hakkında bilgiler sağlar. .Def dosyası DLL oluştururken kullanışlıdır. Olduğundan [bağlayıcı seçenekleri](../../build/reference/linker-options.md) kullanılabilecek modül tanımlama deyimleri yerine .def dosyaları genellikle gerekli değildir. Aynı zamanda [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) belirtmek için bir yol işlevleri verdi.  
  
 İle bağlayıcı aşamasında .def dosyası çağırabileceği [/def (modül tanım dosyasını belirtin)](../../build/reference/def-specify-module-definition-file.md) bağlayıcı seçeneği.  
  
 .Def dosyası kullanarak, hiçbir dışarı aktarma içeren bir .exe dosyası oluşturuluyorsa, çıktı dosyası daha büyük ve daha yavaş yükleniyor hale getirir.  
  
 Bir örnek için bkz: [bir DLL kullanarak DEF dosyaları dışarı aktarma](../../build/exporting-from-a-dll-using-def-files.md).  
  
 Daha fazla bilgi edinmek için aşağıdaki bölümlere bakın:  
  
-   [Modül tanımlama deyimleri kuralları](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [DIŞARI AKTARMA](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [KİTAPLIĞI](../../build/reference/library.md)  
  
-   [ADI](../../build/reference/name-c-cpp.md)  
  
-   [BÖLÜMLER](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [SAPLAMA](../../build/reference/stub.md)  
  
-   [SÜRÜM](../../build/reference/version-c-cpp.md)  
  
-   [Ayrılmış sözcükler](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)  