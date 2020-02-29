---
title: Xcode ve Visual Studio arasındaki eşitleme değişiklikleri
ms.date: 10/17/2019
ms.assetid: c71a4d7c-120e-4559-a114-3a99c4b860a9
ms.openlocfilehash: ab941551c519acee49f658d8a8ff1b9fe0e4ba49
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78177537"
---
# <a name="sync-changes-between-xcode-and-visual-studio"></a>Xcode ve Visual Studio arasındaki eşitleme değişiklikleri

Visual Studio 'da C++ bileşenlerle mobil geliştirme, bilgisayarınızı bilgisayarınız ile Mac arasında eşitlemek için uzak özellikleri içerir. Visual Studio ve Mac makineleriniz eşlendiğinde, Visual Studio 'da projenizi Xcode 'da açmak, kodunuzu Xcode ve Visual Studio arasında taşımak ve geçici Xcode proje dizinini temizlemek için kullanabileceğiniz yeni seçenekler vardır.

Uzak makine seçenekleri kullanmak için projenizin bir iOS uygulaması projesinin olmalıdır ve Visual Studio Mac ile eşleştirilmek Bir Mac 'i eşleştirmeye ilişkin Önkoşullar ve yönergeler için bkz. [iOS kullanarak derlemek için araçları yükleyip yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

## <a name="the-remote-machine-menu"></a>Uzak makine menüsü

**Çözüm Gezgini**, bağlam menüsünü göstermek Için bir iOS uygulama projesine sağ tıklayın. Kullanılabilir uzak seçenekleri göstermek için **uzak makine** öğesini seçin.

![Çözüm Gezgini uzak makine menü öğesi](../cross-platform/media/cppmdd-u2-remotemachine-menu.jpg "Çözüm Gezgini uzak makine menü öğesi")

Bu komutlar, projenizi Xcode 'da açmanıza, yerel değişiklikleri veya tüm projeyi Visual Studio ile Xcode arasında taşımanıza ve uzak makinedeki geçici dosyaları temizleyebilmesine olanak sağlar.

## <a name="open-in-xcode"></a>Xcode 'da aç

Projeyi Xcode 'da Visual Studio 'dan açmak için, **uzak makine** alt menüsünde, eşlenen uzak makinede seçili projeyi açmak Için **Xcode 'da aç** ' ı seçin. `vcremote` sunucusu Mac 'inizde Xcode 'u açmak için kullanılır ve Mac 'inizde projenin bir kopyasını içeren geçici bir dizine gidin. Visual Studio projesi için kullanılan geçici dizini gösteren bir iletişim kutusu görüntüler. Uzak makinede gerçekleştirilen eylemler, Visual Studio 'daki **Çıkış** penceresinde de gösterilir. Bunları görmek için **Çıkış** penceresinin en üstündeki açılan **menüden çıktıyı göster** açılan menüsünde  **C++ Visual uzak makine** ' yi seçmeniz gerekebilir.

![Çıkış penceresi, uzak makine eylemlerini gösterir.](../cross-platform/media/cppmdd-u2-remotemachine-output.png "Çıkış penceresinde uzak makine eylemleri gösterilir")

Mac 'inizde, kodunuzu ve kaynaklarınızı, film şeritlerinizi ve eylemlerinizi düzenlemek için tüm Xcode araçlarını kullanabilirsiniz. Visual Studio 'da, uzak makinede değişikliklerin yapıldığını belirtmek için iOS uygulama projenize "Xcode içinde açılan" ile açıklama eklenir. Düzenlemeleriniz tamamlandıktan sonra uzak konumdan çekme veya artımlı çekme uzak komutlarının değişiklikleri geri Visual Studio projenize kopyalamak için kullanabilirsiniz.

## <a name="push-to-remote-and-incremental-push-to-remote"></a>Uzak ve artımlı anında iletme uzaktan gönderin

Visual Studio'da iOS uygulaması projeniz değişiklikler yaptıysanız anında iletme uzaktan ve uzak komutları için artımlı gönderin eşleştirilmiş uzak makineye değiştirilen proje dosyalarını taşımak için kullanılabilir. Uzak komut gönderme tüm proje dosyaları uzak makineye kopyalar. Artımlı anında uzaktan komut için yalnızca değiştirilen dosyalar uzak makineye kopyalar. Küçük değişiklikler ile büyük projeleri için artımlı komut süreyi ve bant genişliği kaydedebilirsiniz.

Proje dosyalarını Mac 'nize kopyalamak için, Visual Studio 'da **Çözüm Gezgini**' de, içerik menüsünü açmak Için iOS uygulama projesine sağ tıklayın. **Uzak makine** ' yi seçin ve proje dosyalarını Visual Studio 'dan **Mac 'e kopyalamak için uzak ya da** **artımlı gönder** ' i seçin.

## <a name="pull-from-remote-and-incremental-pull-from-remote"></a>Uzak konumdan artımlı ve uzakta çekme isteneceğini

Xcode 'da projenizde değişiklik yaptıktan sonra, projeleri eşitlenmiş halde tutmak için değişiklikleri Visual Studio 'ya geri taşıyın.

Proje dosyalarını Mac 'Inizden kopyalamak için, Visual Studio 'da **Çözüm Gezgini**' de, içerik menüsünü açmak Için iOS uygulama projesine sağ tıklayın. **Uzak makineyi** seçin ve proje dosyalarını Mac 'Inizden Visual Studio 'ya kopyalamak için **uzak veya** **artımlı** alma seçeneklerinden birini belirleyin.

## <a name="clean-remote"></a>Uzak öğeyi Temizle

Uzaktan temizleme komutu, uzak makinedeki geçici proje dizininde bulunan dosyaları silmek için kullanabilirsiniz. Herhangi bir kaynak dosyaları veya derleme ürünler dahil olmak üzere, dizinin içeriklerini Mac'inizde kaldırılır Geri çekme uzaktan veya artımlı çekme uzaktan kullanarak uzaktan temizleme komutu kullanmadan önce Visual Studio için tutmak istediğiniz herhangi bir değişiklik eşitlendiğinden emin olun.

Uzak makinedeki geçici proje dizinini temizlemek için, Visual Studio 'da **Çözüm Gezgini**'de, içerik menüsünü açmak Için iOS uygulama projesine sağ tıklayın. Mac 'Inizden proje dizin dosyalarını kaldırmak için **uzak makine** ' yi seçin ve **Uzaktan temizle** ' yi seçin.
