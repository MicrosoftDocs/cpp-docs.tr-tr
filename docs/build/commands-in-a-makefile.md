---
title: Derleme görevleri dosyası komutları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99e1eb5b4800ff1046ca60d4d4874d386809e2e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="commands-in-a-makefile"></a>Derleme Görevleri Dosyası Komutları
Açıklama bloğu veya çıkarım kuralı bağımlılık güncel ise, çalıştırılacak komut bloğu belirtir. NMAKE görüntüler her komut, çalıştırmadan önce sürece /S, **. Sessiz**, **! CMDSWITCHES**, veya @ kullanılır. NMAKE açıklama blok komutları bloğu tarafından izlenmeyen bir eşleşen çıkarım kuralı için durur.  
  
 Bir komut bloğu her biri kendi satırında bir veya daha fazla komutlarını içerir. Boş bir satır, bağımlılık veya kuralı ve komutları blok arasında yer alabilir. Ancak, yalnızca boşluk veya sekmeler içeren bir satır görüntülenebilir; Bu satır null bir komut olarak yorumlanır ve hata oluşmaz. Boş satırlar arasındaki komut satırları izin verilir.  
  
 Bir komut satırı, bir veya daha fazla boşluk ya da sekme ile başlar. Yeni satır karakterin ardından bir eğik çizgi (\), komut bir alan olarak yorumlanır; ters eğik çizgi bir satırın sonuna bir komut sonraki satıra üzerine devam etmek için kullanın. NMAKE yorumlar ters eğik çizgi gerçek anlamda bir boşluk veya sekmesinde de dahil olmak üzere başka bir karakter ters eğik çizgi izliyorsa.  
  
 Bir komut öncesinde noktalı virgül (;) bir bağımlılık satırı veya çıkarım kuralı, bir komut bloğu izleyen olup olmadığına bakılmaksızın görünebilir:  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
 [Komut değiştiriciler](../build/command-modifiers.md)  
  
 [Dosya adı parçaları sözdizimi](../build/filename-parts-syntax.md)  
  
 [Derleme görevleri dosyasındaki satır içi dosyalar](../build/inline-files-in-a-makefile.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Başvurusu](../build/nmake-reference.md)