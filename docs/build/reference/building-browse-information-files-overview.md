---
title: 'Gözatma Bilgileri Dosyası Derleme: Genel Bakış'
ms.date: 05/06/2019
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: 94cb5865e56e12f51ef4a8598a5df3fcbe69fa0f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078354"
---
# <a name="building-browse-information-files-overview"></a>Gözatma Bilgileri Dosyası Derleme: Genel Bakış

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server. sdf dosyasında otomatik olarak depolanır.

Sembol göz atmaya yönelik gözatma bilgileri oluşturmak için, derleyici projenizdeki her kaynak dosya için bir. sbr dosyası oluşturur, sonra BSCMAKE. EXE. sbr dosyalarını tek bir. bsc dosyasında birleştirir.

. Sbr ve. bsc dosyalarının oluşturulması zaman alır, bu nedenle Visual Studio bu işlevleri varsayılan olarak devre dışı bırakır. Geçerli bilgilere gözatabilmeniz istiyorsanız, üzerinde gezinme seçeneklerini açıp projenizi yeniden oluşturmanız gerekir.

Derleyiciye. sbr dosyaları oluşturmasını söylemek için [/fr](fr-fr-create-dot-sbr-file.md) veya [/fr](fr-fr-create-dot-sbr-file.md) kullanın. . Bsc dosyaları oluşturmak için, komut satırından [BSCMAKE](bscmake-command-line.md) öğesini çağırabilirsiniz. Komut satırından BSCMAKE kullanılması, tarama bilgileri dosyalarının düzenlemesi üzerinde daha kesin denetim sağlar. Daha fazla bilgi için bkz. [BSCMAKE başvurusu](bscmake-reference.md) .

> [!TIP]
>  . Sbr dosya oluşturmayı açabilir ancak. bsc dosya oluşturmayı kapatabilirsiniz. Bu, hızlı derlemeler sağlar, ancak. bsc dosya üretimini açıp projeyi oluşturarak yeni bir. bsc dosyası oluşturmanıza olanak sağlar.

. Bsc dosyasının boyutunu azaltarak bir. bsc dosyası oluşturmak için gereken süre, bellek ve disk alanını azaltabilirsiniz.

Geliştirme ortamında bir tarayıcı dosyası oluşturma hakkında bilgi için bkz. [genel özellik sayfası (proje)](general-property-page-project.md) .

### <a name="to-create-a-smaller-bsc-file"></a>Daha küçük bir. bsc dosyası oluşturmak için

1. Tarama bilgileri dosyasındaki bilgileri dışlamak için [bscmake komut satırı seçeneklerini](bscmake-options.md) kullanın.

1. Derleme veya montaj sırasında bir veya daha fazla. sbr dosyasında yerel sembolleri atlayın.

1. Bir nesne dosyası geçerli hata ayıklama aşamalarınız için gereken bilgileri içermiyorsa, göz at bilgi dosyasını yeniden oluştururken BSCMAKE komutundan. sbr dosyasını atlayın.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Birçok projeden gözatma bilgilerini tek bir tarayıcı dosyasına (. bsc) birleştirmek için

1. Proje düzeyinde. bsc dosyasını oluşturmayın ya da. sbr dosyalarının kırpılmasını engellemek için/n anahtarını kullanın.

1. Tüm projeler derlendikten sonra, tüm. sbr dosyaları için giriş olarak BSCMAKE komutunu çalıştırın. Joker karakterler kabul edilir. Örneğin, C:\X, C:\Y ve C:\Z proje dizinleriniz içinde. sbr dosyaları varsa ve bunları tek bir. bsc dosyasında birleştirmek istiyorsanız BSCMAKE C:\X\\\*. sbr C:\Y\\\*. sbr C:\Z\\\*. sbr/o c:\ whatever_directory \combined.bsc kullanarak birleştirilmiş. bsc dosyasını oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)<br/>
[BSCMAKE Başvurusu](bscmake-reference.md)
