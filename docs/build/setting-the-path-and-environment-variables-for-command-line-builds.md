---
title: Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama
ms.custom: conceptual
ms.date: 11/04/2016
f1_keywords:
- include
- Lib
- Path
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
ms.openlocfilehash: fed3360294bec724af09b87e5abd7c6bb22fa285
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811075"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama

Visual C++ komut satırı derleme araçları özelleştirilmiş çeşitli ortam değişkenleri için yükleme ve yapı yapılandırmanızı gerektirir. Bir C++ iş yükünü Visual Studio yükleyicisi tarafından yüklendiğinde, özel komut dosyaları veya gerekli ortam değişkenlerini ayarlamak, toplu iş dosyaları oluşturur. Yükleyici, bu komut dosyaları sonra bir geliştirici komut istemi penceresi açmak Windows Başlat menüsü kısayolları oluşturmak için kullanır. Bu kısayollar, belirli bir ortam değişkenlerini ayarlama yapılandırması oluşturun. Komut satırı araçlarını kullanmak istediğinizde, bu kısayolları birini çalıştırabilir veya bir düz bir komut istemi penceresi açın ve ardından yapı yapılandırma ortamı kendiniz ayarlamak için özel komut dosyaları çalıştırın. Daha fazla bilgi için [komut satırından MSVC araç takımı kullanın](building-on-the-command-line.md).

Visual C++ komut satırı araçları yolu, TMP, INCLUDE, LIB ve LIBPATH ortam değişkenlerini kullanma ve ayrıca diğer yüklü araçları, platformları ve SDK'ları belirli ortam değişkenlerini kullanın. Basit bir Visual Studio yükleme bile yirmi veya daha fazla ortam değişkenlerini ayarlayabilirsiniz. Bu ortam değişkenlerinin değerlerini yüklemenizi ve kendi seçtiğiniz derleme yapılandırması için özeldir ve ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir olduğundan, bir geliştirici komut istemi kısayolunun veya birini kullanmanızı öneririz bunları Windows ortamında kendiniz ayarlamak yerine bunları ayarlamak için özelleştirilmiş komut dosyaları'nı tıklatın.

Bir geliştirici komut istemi kısayolunun tarafından ayarlanan hangi ortam değişkenleri görmek için SET komutu kullanabilirsiniz. Bir düz bir komut istemi penceresi açın ve bir taban çizgisi için Ayarla komutunun çıkışı yakalayın. Bir geliştirici komut istemi penceresi açın ve karşılaştırma Ayarla komutunun çıkışı yakalayın. Visual Studio IDE yerleşik olanlar gibi bir fark aracının ortam değişkenlerini karşılaştırın ve geliştirici komut istemi tarafından ayarlanan görmek yararlı olabilir. Derleyici ve bağlayıcı tarafından kullanılan özel ortam değişkenleri hakkında daha fazla bilgi için bkz. [CL ortam değişkenleri](reference/cl-environment-variables.md).

> [!NOTE]
>  Birkaç komut satırı araçları ve araç seçenekleri yönetici izni gerektiren. İzin sorunları varsa, bunları kullandığınızda kullanarak Geliştirici komut istemi penceresi açın öneririz **yönetici olarak çalıştır** seçeneği. Windows 10, komut istemi penceresi kısayol menüsünü açmak için sağ tıklayın ve ardından **daha fazla**, **yönetici olarak çalıştır**.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımı kullanın](building-on-the-command-line.md)<br/>
[MSVC bağlayıcı başvurusu](reference/linking.md)<br/>
[MSVC bağlayıcı seçenekleri](reference/linker-options.md)<br/>
[MSVC derleyici başvurusu](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC derleyici seçenekleri](reference/compiler-options.md)
