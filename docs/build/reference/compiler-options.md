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
ms.workload: cplusplus
ms.openlocfilehash: c433abea04ff81c69fe1b73569ea7e043e6e81ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
-   [Alfabetik Listelenmiş Derleyici Seçenekleri](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Kategorilere Göre Listelenen Derleyici Seçenekleri](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>Seçeneklerini belirtme  
 Her derleyici seçeneği konuda geliştirme ortamında nasıl ayarlanabilir anlatılmaktadır. Geliştirme ortamı dışında seçeneklerini belirtme hakkında daha fazla bilgi için bkz:  
  
-   [Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL Komut Dosyaları](../../build/reference/cl-command-files.md)  
  
-   [CL Ortam Değişkenleri](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>İlgili derleme araçları  
 Kullanım [NMAKE](../../build/nmake-reference.md) , çıktı dosyasını oluşturmak için.  
  
 Kullanım [BSCMAKE](../../build/reference/bscmake-reference.md) sınıfı gözatma desteklemek için.  
  
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md) programınızı nasıl yapılandırıldığını de etkiler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Hızlı derleme](../../build/reference/fast-compilation.md)   
 [CL Bağlayıcı Çağırır](../../build/reference/cl-invokes-the-linker.md)