---
title: 'Gözatma Bilgileri Dosyası Derleme: Genel Bakış'
ms.date: 05/06/2019
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: ffacb7aaf9ac1f7ad6fc4cf12ab479099dc57725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320680"
---
# <a name="building-browse-information-files-overview"></a>Gözatma Bilgileri Dosyası Derleme: Genel Bakış

> [!WARNING]
> BSCMAKE hala Visual Studio yüklü olmasına rağmen, artık IDE tarafından kullanılmaz. Visual Studio 2008'den bu yana, göz atma ve sembol bilgileri çözüm klasöründe bir SQL Server .sdf dosyasında otomatik olarak depolanır.

Sembol tarama için gözatma bilgileri oluşturmak için derleyici, projenizdeki her kaynak dosya için bir .sbr dosyası, ardından BSCMAKE oluşturur. EXE.sbr dosyalarını tek bir .bsc dosyasında birleştirir.

.sbr ve .bsc dosyaları oluşturmak zaman alır, bu nedenle Visual Studio varsayılan olarak bu işlevleri kapatır. Geçerli bilgilere göz atmak istiyorsanız, gözatma seçeneklerini açmanız ve projenizi yeniden oluşturmanız gerekir.

Derleyiciye .sbr dosyaları oluşturmasını söylemek için [/FR](fr-fr-create-dot-sbr-file.md) veya [/Fr'yi](fr-fr-create-dot-sbr-file.md) kullanın. .bsc dosyaları oluşturmak için komut satırından [BSCMAKE'yi](bscmake-command-line.md) arayabilirsiniz. Komut satırından BSCMAKE'nin kullanılması, bilgi dosyalarına göz atma nın manipülasyonu üzerinde daha hassas bir kontrol sağlar. Daha fazla bilgi için [BSCMAKE Referans'a](bscmake-reference.md) bakın.

> [!TIP]
> .sbr dosya oluşturmayı açabilir ancak .bsc dosya oluşturmayı kapalı bırakabilirsiniz. Bu, hızlı yapılar sağlar, ancak aynı zamanda .bsc dosya oluşturma yı açıp projeyi oluşturarak hızlı bir şekilde yeni bir .bsc dosyası oluşturmanıza olanak tanır.

.bsc dosyasının boyutunu azaltarak .bsc dosyası oluşturmak için gereken zamanı, belleği ve disk alanını azaltabilirsiniz.

Geliştirme ortamında bir tarayıcı dosyasının nasıl oluşturulabildiğini öğrenmek için [Genel Özellik Sayfasına (Proje)](general-property-page-project.md) bakın.

### <a name="to-create-a-smaller-bsc-file"></a>Daha küçük bir .bsc dosyası oluşturmak için

1. Bilgileri gözatma bilgileri dosyasından hariç tutmak için [BSCMAKE komut satırı seçeneklerini](bscmake-options.md) kullanın.

1. Derleme veya derleme yaparken bir veya daha fazla .sbr dosyasında yerel sembolleri atayın.

1. Bir nesne dosyası hata ayıklama nın geçerli aşaması için gerekli bilgileri içermiyorsa, gözatma bilgileri dosyasını yeniden oluşturunuzda .sbr dosyasını BSCMAKE komutundan atla.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Çeşitli projelerdeki gözatma bilgilerini tek bir tarayıcı dosyasında birleştirmek için (.bsc)

1. .bsc dosyasını proje düzeyinde oluşturmayın veya .sbr dosyalarının kesildikten korunmak için /n anahtarını kullanın.

1. Tüm projeler inşa edildikten sonra, bscmake'i tüm .sbr dosyalarıyla birlikte çalıştırın. Joker karakterler kabul edilir. Örneğin, c:\x, c:\Y ve C:\Z ve c:\Z dosyalarıyla birlikte proje dizinleriniz varsa ve bunları tek bir .bsc dosyasında birleştirmek istiyorsanız, bscMAKE C:\X .sbr\\\*C:\Y\\\*.sbr C:\Z\\\*.sbr /o c:\whatever_directory\combined.bsc'yi kullanarak birleştirilmiş .bsc dosyasını oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC Oluşturma Araçları](c-cpp-build-tools.md)<br/>
[BSCMAKE Başvurusu](bscmake-reference.md)
