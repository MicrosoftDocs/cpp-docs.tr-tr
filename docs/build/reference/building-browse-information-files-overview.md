---
title: "Yapı gözatma bilgileri dosyaları: Genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5b369d5a708e0ee56df635234c68ee88a31af48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="building-browse-information-files-overview"></a>Gözatma Bilgileri Dosyası Derleme: Genel Bakış
Simgenin tarama için gözatma bilgilerini oluşturmak için derleyici projenizde sonra BSCMAKE her kaynak dosya için .sbr dosyası oluşturur. EXE .sbr dosyaları bir .bsc dosyasına art arda ekler.  
  
 Varsayılan olarak bu işlevler Visual C++ kapanmadan şekilde .sbr ve .bsc dosyaları oluşturmak zaman alır. Geçerli bilgileri Gözat isterseniz, Gözat seçenekleri Aç ve projenizi yeniden oluşturun.  
  
 Kullanım [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) veya [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) .sbr dosyaları oluşturmak için derleyici bildirmek için. .BSC dosyaları oluşturmak için çağırabilirsiniz [BSCMAKE](../../build/reference/bscmake-command-line.md) komut satırından. BSCMAKE komut satırından kullanma gözatma bilgileri dosyaları işleme üzerinde daha kesin bir denetim sağlar. Bkz: [BSCMAKE başvurusu](../../build/reference/bscmake-reference.md) daha fazla bilgi için.  
  
> [!TIP]
>  .Sbr dosyası oluşturma üzerinde kapatma ancak .bsc dosyası oluşturma devre dışı bırakın. Bu, hızlı oluşturur, ancak ayrıca yeni .bsc dosyası üzerinde .bsc dosyası oluşturma kapatarak ve proje derleme hızlı bir şekilde oluşturmanızı sağlar sağlar.  
  
 Süresi, bellek ve .bsc dosyasının boyutunu azaltarak .bsc dosyasını oluşturmak için gerekli disk alanını azaltabilirsiniz.  
  
 Bkz: [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md) geliştirme ortamında tarayıcı dosyasının nasıl oluşturulacağı hakkında bilgi için.  
  
### <a name="to-create-a-smaller-bsc-file"></a>Daha küçük bir .bsc dosyası oluşturmak için  
  
1.  Kullanım [BSCMAKE komut satırı seçenekleri](../../build/reference/bscmake-options.md) gözatma bilgileri dosyasından bilgi dışlanacak.  
  
2.  Derleme veya birleştirme, bir veya daha fazla .sbr dosyaları yerel semboller atlayın.  
  
3.  Gözatma bilgileri dosyası yeniden oluşturduğunuzda bir nesne dosyası hata ayıklama, geçerli aşaması için gereken bilgileri içermiyorsa, kendi .sbr dosyası BSCMAKE komut yok sayın.  
  
### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Bir tarayıcı dosyasına (.bsc) birkaç projelerinden gözatma bilgileri birleştirmek için  
  
1.  Yoktur proje düzeyinde .bsc dosyası derleme veya /n anahtarı kesilmiş gelen .sbr dosyaları engellemek için kullanabilirsiniz.  
  
2.  Tüm projeleri yerleşik sonra BSCMAKE tüm .sbr dosyaları ile giriş olarak çalıştırın. Joker karakterler kabul edilir. Örneğin, bunları ve tüm bir .bsc dosyada birleştirmek istediğinizi .sbr dosyaları ile proje dizinleri C:\X, C:\Y ve C:\Z olsaydı, ardından BSCMAKE C:\X kullanın\\*.sbr C:\Y\\\*.sbr C:\Z\\\*. Birleşik .bsc dosyasını oluşturmak için /o c:\whatever_directory\combined.bsc sbr.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ derleme araçları](../../build/reference/c-cpp-build-tools.md)   
 [BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)