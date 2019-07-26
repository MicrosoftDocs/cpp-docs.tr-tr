---
title: Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama
ms.custom: conceptual
ms.date: 07/24/2019
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
ms.openlocfilehash: 6e7882b169805e3c62596341986a83d476ac5ec1
ms.sourcegitcommit: ce3393846c86e7905ff0c86e4cd6610476809585
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68492148"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama

Microsoft C++ (MSVC) komut satırı derleme araçları, yüklemeniz ve derleme yapılandırmanız için özelleştirilmiş çeşitli ortam değişkenleri gerektirir. Visual Studio C++ yükleyicisi tarafından bir iş yükü yüklendiğinde, gerekli ortam değişkenlerini ayarlamak için özelleştirilmiş komut dosyaları veya toplu iş dosyaları oluşturur. Yükleyici daha sonra bu komut dosyalarını kullanarak bir geliştirici komut istemi penceresi açmak için Windows Başlat menüsüne kısayollar oluşturur. Bu kısayollar, belirli bir yapı yapılandırması için ortam değişkenlerini ayarlar. Komut satırı araçlarını kullanmak istediğinizde, Bu kısayollardan birini çalıştırabilir veya düz bir komut istemi penceresi açıp, derleme yapılandırma ortamını kendiniz ayarlamak için özel komut dosyalarından birini çalıştırabilirsiniz. Daha fazla bilgi için, bkz. [MSVC araç takımını komut satırından kullanma](building-on-the-command-line.md). Komut dosyalarını düz bir komut istemiyle kullanmak için, [Geliştirici komut dosyası konumları](building-on-the-command-line.md#developer_command_file_locations)başlıklı bölüme bakın.

MSVC komut satırı araçları PATH, TMP, ıNCLUDE, LIB ve LıBPATH ortam değişkenlerini kullanır ve ayrıca yüklü araçlara, platformlarınıza ve SDK 'larınıza özgü diğer ortam değişkenlerini kullanır. Basit bir Visual Studio yüklemesi de yirmi veya daha fazla ortam değişkeni ayarlayabilir. Bu ortam değişkenlerinin değerleri yüklemenize ve yapı yapılandırmanıza özgü olduğundan ve ürün güncelleştirmeleri ya da yükseltmeler tarafından değiştirilebildiğinden, geliştirici komut istemi kısayolunu veya şunlardan birini kullanmanız önemle önerilir bunları Windows ortamında ayarlamak yerine, özelleştirilmiş komut dosyaları.

Bir geliştirici komut istemi kısayoluyla ayarlanan ortam değişkenlerini görmek için, SET komutunu kullanabilirsiniz. Düz bir komut istemi penceresi açın ve bir taban çizgisi için SET komutunun çıkışını yakalayın. Bir geliştirici komut istemi penceresi açın ve, karşılaştırma için SET komutunun çıkışını yakalayın. Visual Studio IDE içinde yerleşik olan bir fark aracı, ortam değişkenlerini karşılaştırmak ve geliştirici komut istemi tarafından ayarlanan öğeleri görmek için yararlı olabilir. Derleyici ve bağlayıcı tarafından kullanılan belirli ortam değişkenleri hakkında daha fazla bilgi için bkz. [CL ortam değişkenleri](reference/cl-environment-variables.md).

> [!NOTE]
>  Birkaç komut satırı aracı veya araç seçeneği, yönetici izni gerektirebilir. Bunları kullandığınızda izin sorunlarınız varsa, **yönetici olarak çalıştır** seçeneğini kullanarak Geliştirici komut istemi penceresini açmanız önerilir. Windows 10 ' da, komut istemi penceresinin kısayol menüsünü açmak için sağ tıklayın ve **daha**sonra **yönetici olarak çalıştır**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımını kullanma](building-on-the-command-line.md)<br/>
[MSVC bağlayıcı başvurusu](reference/linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](reference/linker-options.md)<br/>
[MSVC Derleyicisi Başvurusu](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
