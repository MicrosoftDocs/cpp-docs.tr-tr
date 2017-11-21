---
title: "Derleyici Seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler
- IPF Visual C++ compiler
- Itanium Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 490814f85199450d4261bf4071184b75b5ea10c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-options"></a>Derleyici Seçenekleri
cl.exe Microsoft C ve C++ Derleyicileri ve bağlayıcı denetleyen bir araçtır. cl.exe yalnızca Microsoft Visual Studio desteklendiği işletim sistemlerinin üzerinde çalıştırılabilir.  
  
> [!NOTE]
>  Bu araç yalnızca başlatabilirsiniz [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] komut istemi. Bir sistem komut istemi veya dosya Gezgini başlatılamıyor.  
  
 Derleyicileri ortak nesne dosyası biçimi (COFF) nesne (.obj) dosyaları üretir. Bağlayıcı yürütülebilir dosyanın (.exe) dosyaları veya dinamik bağlantı kitaplıklarını (DLL'ler) oluşturur.  
  
 Tüm derleyici seçenekleri büyük küçük harfe duyarlı olduğunu unutmayın.  
  
 Bağlantılandırmadan derleme için kullanmak [/c](../../build/reference/c-compile-without-linking.md).  
  
## <a name="finding-an-option"></a>Bir seçenek bulma  
 Belirli derleyici seçeneği bulmak için aşağıdaki listede birine bakın:  
  
-   [Alfabetik olarak listelenen derleyici seçenekleri](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Kategoriye göre listelenen derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>Seçeneklerini belirtme  
 Her derleyici seçeneği konuda geliştirme ortamında nasıl ayarlanabilir anlatılmaktadır. Geliştirme ortamı dışında seçeneklerini belirtme hakkında daha fazla bilgi için bkz:  
  
-   [Derleyici komut satırı sözdizimi](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL komut dosyaları](../../build/reference/cl-command-files.md)  
  
-   [CL ortam değişkenleri](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>İlgili derleme araçları  
 Kullanım [NMAKE](../../build/nmake-reference.md) , çıktı dosyasını oluşturmak için.  
  
 Kullanım [BSCMAKE](../../build/reference/bscmake-reference.md) sınıfı gözatma desteklemek için.  
  
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md) programınızı nasıl yapılandırıldığını de etkiler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Hızlı derleme](../../build/reference/fast-compilation.md)   
 [CL bağlayıcı çağırır](../../build/reference/cl-invokes-the-linker.md)