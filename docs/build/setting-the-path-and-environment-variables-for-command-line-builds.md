---
title: Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama | Microsoft Docs
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- include
- Lib
- Path
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e4b24e3ec209273b0f547c99685e8e804a74bc0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724275"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama

Visual C++ komut satırı derleme araçları özelleştirilmiş çeşitli ortam değişkenleri için yükleme ve yapı yapılandırmanızı gerektirir. Bir C++ iş yükünü Visual Studio yükleyicisi tarafından yüklendiğinde, özel komut dosyaları veya gerekli ortam değişkenlerini ayarlamak, toplu iş dosyaları oluşturur. Yükleyici, bu komut dosyaları sonra bir geliştirici komut istemi penceresi açmak Windows Başlat menüsü kısayolları oluşturmak için kullanır. Bu kısayollar, belirli bir ortam değişkenlerini ayarlama yapılandırması oluşturun. Komut satırı araçlarını kullanmak istediğinizde, bu kısayolları birini çalıştırabilir veya bir düz bir komut istemi penceresi açın ve ardından yapı yapılandırma ortamı kendiniz ayarlamak için özel komut dosyaları çalıştırın. Daha fazla bilgi için [komut satırında C/C++ kodu derleme](building-on-the-command-line.md).

Visual C++ komut satırı araçları yolu, TMP, INCLUDE, LIB ve LIBPATH ortam değişkenlerini kullanma ve ayrıca diğer yüklü araçları, platformları ve SDK'ları belirli ortam değişkenlerini kullanın. Basit bir Visual Studio yükleme bile yirmi veya daha fazla ortam değişkenlerini ayarlayabilirsiniz. Bu ortam değişkenlerinin değerlerini yüklemenizi ve kendi seçtiğiniz derleme yapılandırması için özeldir ve ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir olduğundan, bir geliştirici komut istemi kısayolunun veya birini kullanmanızı öneririz bunları Windows ortamında kendiniz ayarlamak yerine bunları ayarlamak için özelleştirilmiş komut dosyaları'nı tıklatın.

Bir geliştirici komut istemi kısayolunun tarafından ayarlanan hangi ortam değişkenleri görmek için SET komutu kullanabilirsiniz. Bir düz bir komut istemi penceresi açın ve bir taban çizgisi için Ayarla komutunun çıkışı yakalayın. Bir geliştirici komut istemi penceresi açın ve karşılaştırma Ayarla komutunun çıkışı yakalayın. Visual Studio IDE yerleşik olanlar gibi bir fark aracının ortam değişkenlerini karşılaştırın ve geliştirici komut istemi tarafından ayarlanan görmek yararlı olabilir. Derleyici ve bağlayıcı tarafından kullanılan özel ortam değişkenleri hakkında daha fazla bilgi için bkz. [CL ortam değişkenleri](../build/reference/cl-environment-variables.md) ve [LINK ortam değişkenleri](../build/reference/link-environment-variables.md).

> [!NOTE]
>  Birkaç komut satırı araçları ve araç seçenekleri yönetici izni gerektiren. İzin sorunları varsa, bunları kullandığınızda kullanarak Geliştirici komut istemi penceresi açın öneririz **yönetici olarak çalıştır** seçeneği. Windows 10, komut istemi penceresi kısayol menüsünü açmak için sağ tıklayın ve ardından **daha fazla**, **yönetici olarak çalıştır**.

## <a name="see-also"></a>Ayrıca Bkz.

[Komut satırında C/C++ kodu derleme](../build/building-on-the-command-line.md)<br/>
[Bağlama](../build/reference/linking.md)<br/>
[Bağlayıcı Seçenekleri](../build/reference/linker-options.md)<br/>
[C/C++ Programı Derleme](../build/reference/compiling-a-c-cpp-program.md)<br/>
[Derleyici Seçenekleri](../build/reference/compiler-options.md)