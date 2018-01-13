---
title: "CL bağlayıcı çağırır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32a3bdd1e227b894ca5a32ddfaa8c46a478a19f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cl-invokes-the-linker"></a>CL Bağlayıcı Çağırır
CL bağlayıcı /c seçeneği kullanılmıyorsa derledikten sonra otomatik olarak çağırır. CL bağlayıcı için derleme sırasında oluşturulan .obj dosyaları adlarını ve komut satırında belirtilen dosyaların adlarını geçirir. Bağlayıcı bağlantı ortam değişkeninde listelenen seçenekleri kullanır. / Link seçeneği CL komut satırında bağlayıcı seçeneklerini belirtmek için kullanabilirsiniz. / Link seçeneği izleyin seçenekleri bağlantı ortam değişkeninde geçersiz kılar. Aşağıdaki tabloda seçeneklerinde bağlama engelleyin.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|/c|Bağlantılandırmadan derleme|  
|/ E, /EP, /P|Derleme veya bağlama önişle|  
|/ZG|İşlev prototipleri üret|  
|/ZS|Sözdizimini denetleyin|  
  
 Bağlama hakkında daha ayrıntılı bilgi için bkz: [bağlayıcı seçenekleri](../../build/reference/linker-options.md).  
  
## <a name="example"></a>Örnek  
 Üç C kaynak dosyaları derleme varsayalım: MAIN.c, MOD1.c ve MOD2.c. Her dosya farklı bir dosyada tanımlanan bir işlev çağrısı içeriyor:  
  
-   MAIN.c işlevi çağırır `func1` MOD1.c ve işlev `func2` MOD2.c içinde.  
  
-   MOD1.c çağırır standart kitaplığı işlevleri `printf_s` ve `scanf_s`.  
  
-   MOD2.c çağırır adlı grafik işlevleri `myline` ve `mycircle`, MYGRAPH.lib adlı bir kitaplık içinde tanımlanır.  
  
 Bu program oluşturmak için şu komut satırıyla derleyin:  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL ilk C kaynak dosyalarını derler ve MAIN.obj, MOD1.obj ve MOD2.obj nesne dosyaları oluşturur. Derleyici standart kitaplığı adı her .obj dosyasına yerleştirir. Daha fazla ayrıntı için bkz: [çalışma zamanı kitaplığını kullan](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 CL bağlayıcı adı MYGRAPH.lib, birlikte .obj dosyaları adlarını geçirir. Bağlayıcı gibi dış başvuruları çözer:  
  
1.  MAIN.obj, başvuru içinde `func1` MOD1.obj içinde; tanımı kullanılarak çözümlendi referansı `func2` içinde MOD2.obj tanımı kullanılarak çözümlenir.  
  
2.  MOD1.obj, başvuruları içinde `printf_s` ve `scanf_s` içinde MOD1.obj adlı bağlayıcı bulur Kitaplığı'nda tanımları kullanılarak çözümlenir.  
  
3.  MOD2.obj, başvuruları içinde `myline` ve `mycircle` MYGRAPH.lib içinde tanımları kullanılarak çözümlenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)