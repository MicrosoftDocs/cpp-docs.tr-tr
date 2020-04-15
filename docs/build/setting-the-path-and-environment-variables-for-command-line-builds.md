---
title: Komut Satırı Yapılar için Yol ve Çevre Değişkenlerini Ayarlama
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
ms.openlocfilehash: aeafe806e5d29b89c243586974814aa7cfc16d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335579"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Komut Satırı Yapılar için Yol ve Çevre Değişkenlerini Ayarlama

Microsoft C++ (MSVC) komut satırı oluşturma araçları, yükleme niz ve yapılandırmanız için özelleştirilmiş çeşitli ortam değişkenleri gerektirir. Visual Studio yükleyicisi tarafından C++ iş yükü yüklendiğinde, gerekli ortam değişkenlerini ayarlayan özelleştirilmiş komut dosyaları veya toplu dosyalar oluşturur. Yükleyici daha sonra bir geliştirici komut istemi penceresi açmak için Windows Başlat menüsü için kısayollar oluşturmak için bu komut dosyalarını kullanır. Bu kısayollar, belirli bir yapı yapılandırması için ortam değişkenlerini ayarlar. Komut satırı araçlarını kullanmak istediğinizde, bu kısayollardan birini çalıştırabilir veya düz komut istemi penceresini açıp yapı yapılandırma ortamını kendiniz ayarlamak için özel komut dosyalarından birini çalıştırabilirsiniz. Daha fazla bilgi için [bkz.](building-on-the-command-line.md) Komut dosyalarını düz komut istemiyle kullanmak için [Geliştirici komut dosyası konumları](building-on-the-command-line.md#developer_command_file_locations)başlıklı bölüme bakın.

MSVC komut satırı araçları PATH, TMP, INCLUDE, LIB ve LIBPATH ortam değişkenlerini kullanır ve ayrıca yüklü araçlarınız, platformlarınız ve SDK'larınıza özgü diğer ortam değişkenlerini de kullanır. Basit bir Visual Studio yüklemesi bile yirmi veya daha fazla ortam değişkeni ayarlayabilir. Bu ortam değişkenlerinin değerleri yüklemenize ve yapı yapılandırmaseçiminize özgü olduğundan ve ürün güncelleştirmeleri veya yükseltmelerle değiştirilebildiği için, windows ortamında kendiniz ayarlamak yerine geliştirici komut istemi kısayolu veya bunları ayarlamak için özelleştirilmiş komut dosyalarından birini kullanmanızı öneririz.

Geliştirici komut istemi kısayolu tarafından hangi ortam değişkenlerinin ayarlanabiliyorsanız, SET komutunu kullanabilirsiniz. Düz komut istemi penceresi açın ve bir taban çizgisi için SET komutunun çıktısını yakalayın. Geliştirici komut istemi penceresi açın ve karşılaştırma için SET komutunun çıktısını yakalayın. Visual Studio IDE'de yerleşik olan gibi bir diff aracı, ortam değişkenlerini karşılaştırmak ve geliştirici komut istemi tarafından ne ayarlı olduğunu görmek için yararlı olabilir. Derleyici ve bağlayıcı tarafından kullanılan belirli ortam değişkenleri hakkında bilgi için [CL Çevre Değişkenleri'ne](reference/cl-environment-variables.md)bakın.

> [!NOTE]
> Birkaç komut satırı aracı veya araç seçeneği Yönetici izni gerektirebilir. Bunları kullanırken izin sorunlarınız varsa, **Yönetici olarak Çalıştır** seçeneğini kullanarak geliştirici komut istemi penceresini açmanızı öneririz. Windows 10'da komut istemi penceresiiçin kısayol menüsünü açmak için sağ tıklatın ve ardından **Daha Fazla**, Yönetici **Olarak Çalıştır'ı**seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırından MSVC araç takımını kullanma](building-on-the-command-line.md)<br/>
[MSVC bağlayıcı başvurusu](reference/linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](reference/linker-options.md)<br/>
[MSVC Derleyicisi Başvurusu](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
