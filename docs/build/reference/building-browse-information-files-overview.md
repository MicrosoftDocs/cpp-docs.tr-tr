---
title: 'Yapı gözatma bilgisi dosyalarının: Genel bakış | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 493f25ba6839058a9ff749cb0dbb3853b1b16494
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712302"
---
# <a name="building-browse-information-files-overview"></a>Gözatma Bilgileri Dosyası Derleme: Genel Bakış

Sembol tarama için gözatma bilgisi oluşturmak için derleyicinin .sbr dosyası her kaynak dosyası için projenizde ardından BSCMAKE oluşturur. EXE .bsc dosyasına .sbr dosyaları art arda ekler.

Varsayılan olarak Visual C++ bu işlevler devre dışı bırakır, böylece .sbr ve .bsc dosyaları oluşturmak zaman alır. Geçerli bilgilerine göz atmak istiyorsanız, göz atma Seçenekleri'ni açın ve projenizi yeniden derleyin.

Kullanım [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) veya [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) .sbr dosyaları oluşturmak için derleyicinin söylemek için. .BSC dosyaları oluşturmak için çağırabilirsiniz [BSCMAKE](../../build/reference/bscmake-command-line.md) komut satırından. BSCMAKE komut satırından kullanarak gözatma bilgisi dosyalarının işlenmesini üzerinde daha kesin denetim verir. Bkz: [BSCMAKE başvurusu](../../build/reference/bscmake-reference.md) daha fazla bilgi için.

> [!TIP]
>  .Sbr dosyası oluşturma hakkında kapatma ancak .bsc dosyası oluşturma devre dışı bırakın. Bu hızlı oluşturulur, ancak ayrıca yeni .bsc dosyası .bsc dosyası nesil kapatma ve projeyi derlemek hızla oluşturmanızı sağlayan sağlar.

İstediğiniz zaman, bellek ve .bsc dosyası boyutunu azaltarak .bsc dosyasını oluşturmak için gerekli disk alanını azaltabilirsiniz.

Bkz: [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md) geliştirme ortamında bir tarayıcı dosyasının nasıl oluşturulacağı hakkında bilgi için.

### <a name="to-create-a-smaller-bsc-file"></a>Daha küçük .bsc dosyasını oluşturmak için

1. Kullanım [BSCMAKE komut satırı seçenekleri](../../build/reference/bscmake-options.md) gözatma bilgileri dosyasından bilgi dışlanacak.

1. Derleme veya derleyerek, bir veya daha fazla .sbr dosyaları yerel semboller yok sayın.

1. Bir nesne dosyası hata ayıklama, geçerli aşama için gerekli bilgiler yoksa, gözatma bilgisi dosyası yeniden oluşturduğunuzda, .sbr dosyası BSCMAKE komut atlayın.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Birkaç proje (.bsc) bir tarayıcı dosyasına göz atma bilgileri birleştirmek için

1. Yoksa proje düzeyinde .bsc dosyası derleme veya /n anahtar .sbr dosyaları kesildi gelen önlemek için kullanabilirsiniz.

1. Tüm projeler oluşturulur sonra BSCMAKE tüm .sbr dosyaları ile giriş olarak çalıştırın. Joker karakterler kabul edilir. Örneğin, bunları ve bunların tümünü bir .bsc dosyada birleştirmek istediğinizi .sbr dosyaları ile proje dizinleri C:\X C:\Y ve C:\Z olsaydı, ardından BSCMAKE C:\X kullanın\\\*.sbr C:\Y\\\*.sbr C:\Z\\ \*.sbr /o c:\whatever_directory\combined.bsc birleşik .bsc dosyasını oluşturmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)<br/>
[BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)
