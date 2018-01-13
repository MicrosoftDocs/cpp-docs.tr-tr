---
title: "Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- include
- Lib
- Path
dev_langs: C++
helpviewer_keywords:
- environment variables [C++]
- VCVARS32.bat file
- cl.exe compiler [C++], environment variables
- LINK tool [C++], environment variables
- PATH reserved word
- INCLUDE reserved word
- LINK tool [C++], path
- LIB environment variable
- compiling source code [C++], from command line
- environment variables [C++], CL compiler
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76fa1a14b4fd60f249ab015f6618e386bda7c86f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama

Visual C++ komut satırı derleme araçları özelleştirilmiş birkaç ortam değişkenleri için yükleme ve yapı yapılandırmanızı gerektirir. C++ iş yükü yüklü olduğunda tarafından [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yükleyici, oluşturduğu özelleştirilmiş komut dosyaları ya da gerekli ortam değişkenlerini ayarlama toplu iş dosyaları,. Yükleyici, bu komut dosyaları sonra bir geliştirici komut istemi penceresi açmak Windows Başlat menüsündeki kısayolları oluşturmak için kullanır. Derleme yapılandırması kısayolların belirli bir ortam değişkenleri ayarlayın. Komut satırı araçlarını kullanmak istediğinizde, bu kısayol birini çalıştırabilir veya bir düz bir komut istemi penceresi açın ve yapı yapılandırma ortamını ayarlamak için özel komut dosyaları birini çalıştırın. Daha fazla bilgi için bkz: [komut satırında C/C++ kod derleme](building-on-the-command-line.md).  
  
Visual C++ komut satırı araçları YOLUNU, TMP, Ekle, LIB ve LIBPATH ortam değişkenlerini kullanma ve ayrıca yüklenen araçlar, platformlar ve SDK'ları belirli diğer ortam değişkenlerini kullanın. Basit bir bile [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yükleme yirmi ya da daha fazla ortam değişkenlerini ayarlama. Bu ortam değişkenlerinin değerlerini yüklemenizi ve yapı yapılandırma seçiminizi özeldir ve ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir olduğundan, geliştirici komut istemi kısayoluna veya birini kullanmanızı öneririz bunları, bunları Windows ortamında kendiniz yerine ayarlamak için özelleştirilmiş komut dosyaları. 

Hangi ortam değişkenleri Geliştirici komut istemi kısayol tarafından ayarlanan görmek için SET komutunu kullanabilirsiniz. Düz komut istemi penceresi açın ve bir taban çizgisi için KÜMESİ komutunun çıkışını yakalayın. Bir geliştirici komut istemi penceresi açın ve karşılaştırma KÜMESİ komutunun çıkışını yakalayın. Fark aracı Visual Studio IDE içinde yerleşik olanlar gibi ortam değişkenleri karşılaştırın ve geliştirici komut istemi tarafından ayarlanan görmek yararlı olabilir. Derleyici ve bağlayıcı tarafından kullanılan belirli ortam değişkenleri hakkında daha fazla bilgi için bkz: [CL ortam değişkenleri](../build/reference/cl-environment-variables.md) ve [LINK ortam değişkenleri](../build/reference/link-environment-variables.md).  
  
> [!NOTE]
>  Çeşitli komut satırı araçları ve aracı seçenekleri yönetici izni gerektirebilir. İzin sorunları varsa, bunları kullandığınızda kullanarak Geliştirici komut istemi penceresi açın öneririz **yönetici olarak çalıştır** seçeneği. Windows 10, komut istemi penceresi için kısayol menüsünü açmak için sağ tıklatın ve ardından **daha fazla**, **yönetici olarak çalıştır**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Komut satırında C/C++ kodu derleme](../build/building-on-the-command-line.md)   
[Bağlama](../build/reference/linking.md)   
[Bağlayıcı seçenekleri](../build/reference/linker-options.md)   
[C/C++ programını derleme](../build/reference/compiling-a-c-cpp-program.md)   
[Derleyici Seçenekleri](../build/reference/compiler-options.md)