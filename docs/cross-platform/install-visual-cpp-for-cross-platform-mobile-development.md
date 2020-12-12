---
description: 'Hakkında daha fazla bilgi edinin: C++ ile platformlar arası mobil geliştirme'
title: C++ ile platformlar arası mobil geliştirmeyi yükleme
ms.date: 10/17/2019
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
ms.openlocfilehash: 45059cbadcd8e8c304c65262ffcb89bf767095e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319228"
---
# <a name="install-cross-platform-mobile-development-with-c"></a>C++ ile platformlar arası mobil geliştirmeyi yükleme

Visual Studio 'da C++ kullanarak Windows Masaüstü uygulamaları, Evrensel Windows Platformu (UWP) uygulamaları ve Linux uygulamaları oluşturabilirsiniz. Şimdi de Android ve iOS için C++ uygulamaları oluşturabilirsiniz. C++ iş yüküne **sahip mobil geliştirme** , Visual Studio 'da yüklenebilen bir bileşen kümesidir. Platformlar arası iOS, Android ve UWP Visual Studio şablonlarını içerir. İş yükü, hızlıca kullanmaya başlamak için ihtiyacınız olan platformlar arası araçları ve SDK 'Ları yükleme. Bunları kendiniz bulmanız, indirmeniz ve yapılandırmanız gerekmez. Bu araçları, Visual Studio 'da, platformlar arası projelerinizi kolayca oluşturmak, düzenlemek, hatalarını ayıklamak ve test etmek için kullanabilirsiniz.

Bu makalede, Visual Studio kullanarak C++ ' da platformlar arası uygulamalar geliştirmek için gereken araçların ve üçüncü taraf yazılımların nasıl yükleneceği açıklanır. Genel bakış için bkz. [platformlar arası mobil Visual C++](https://visualstudio.microsoft.com/vs/features/cplusplus-mdd/)

## <a name="requirements"></a>Gereksinimler

::: moniker range="msvc-150"

- Yükleme gereksinimleri için bkz. [Visual Studio ürün ailesi sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs).

   > [!IMPORTANT]
   > Windows 7 veya Windows Server 2008 R2 kullanıyorsanız, Windows Masaüstü uygulamaları, Android yerel etkinlik uygulamaları ve kitaplıkları ve iOS için uygulamalar ve kod kitaplıkları için kod geliştirebilirsiniz, ancak Windows Mağazası veya UWP uygulamaları kullanamazsınız.

::: moniker-end
::: moniker range=">=msvc-160"

- Yükleme gereksinimleri için bkz. [Visual Studio ürün ailesi sistem gereksinimleri](/visualstudio/releases/2019/system-requirements).

   > [!IMPORTANT]
   > Windows 7 veya Windows Server 2008 R2 kullanıyorsanız, Windows Masaüstü uygulamaları, Android yerel etkinlik uygulamaları ve kitaplıkları ve iOS için uygulamalar ve kod kitaplıkları için kod geliştirebilirsiniz, ancak Windows Phone veya UWP uygulamaları kullanamazsınız.

::: moniker-end

Belirli cihaz platformları için uygulamalar oluşturmak üzere bazı ek gereksinimler vardır:

- Android SDK ile birlikte gelen x86 Android öykünücüleri, Intel Hardware Accelerated Execution Manager (HAXM) gibi donanım hızlandırmasını kullanan bilgisayarlarda en iyi şekilde çalışır. Daha fazla bilgi için bkz. [öykünücü performansı Için donanım hızlandırma (Hyper-V & HAXM)](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin&pivots=windows).

- İOS için kod oluşturma, bir Apple KIMLIĞI, bir iOS Geliştirici Programı hesabı ve [Xcode](https://developer.apple.com/xcode/) sürüm 10,2 veya sonrakı sürümlerini OS X Mavericks (sürüm 10,9) veya sonraki sürümlerde çalıştıran bir Mac bilgisayar gerektirir. Yükleme adımlarının bağlantısı için bkz. [iOS Için yükleme araçları](#install-tools-for-ios).

- Windows Phone Öykünücüler, Hyper-V ' y i çalıştıran bir bilgisayar gerektirir. Öykünücüleri yüklemeden ve çalıştırmadan önce Windows 'daki Hyper-V özelliğinin etkinleştirilmesi gerekir. Daha fazla bilgi için öykünücü [sistem gereksinimlerine](/visualstudio/cross-platform/system-requirements-for-the-visual-studio-emulator-for-android)bakın.

## <a name="get-the-tools"></a>Araçları edinme

C++ ile mobil geliştirme, Visual Studio Community, Professional ve Enterprise sürümlerinde kullanılabilir. Visual Studio 'yu almak için [Visual Studio İndirmeleri](https://visualstudio.microsoft.com/downloads/) sayfasına gidin. Platformlar arası mobil geliştirme araçları, Visual Studio 2015 ' den itibaren kullanılabilir.

## <a name="install-the-tools"></a>Araçları yükler

Visual Studio Yükleyicisi, C++ iş yüküne **sahip bir mobil geliştirme** içerir. Bu iş yükü, Visual Studio 'da Android ve iOS geliştirmesi için gereken C++ dil araçlarını, şablonları ve bileşenleri yüklüyor. Android derlemeler ve hata ayıklama için gereken GCC ve Clang araç kümelerini içerir. İş yükü, iOS geliştirmesi için bir Mac ile iletişim kurmak üzere Android SDK ve bileşenlerini yüklüyor. Ayrıca iOS ve Android uygulama geliştirmeyi desteklemek için gereken üçüncü taraf araçları ve yazılım geliştirme setleri de yüklenir. Bu üçüncü taraf araçların çoğu, Android Platform desteği için gereken açık kaynaklı yazılımdır.

- Android platformunu hedefleyen C++ kodu derlemek için Android yerel geliştirme seti (NDK), Apache Ant ve C++ Android geliştirme araçları gerekir.

  > [!NOTE]
  > Android NDK 'deki bazı araçlar dosya yollarında ve dosya adlarında Unicode karakterlerini desteklemez. Bir proje veya kaynak dosyasında, yolunda veya dosya adında Unicode karakterler varsa, proje derlenmeyecektir.

- Google Android Emulator ve Intel Hardware Accelerated Execution Manager (HAXM) isteğe bağlıdır, ancak önerilir. (Intel HAXM sürücüleri yalnızca Intel işlemcilerde çalışır ve Hyper-V dahil bazı VM 'lerle uyumsuzdur.) Doğrudan bir Android cihazında geliştirme ve hata ayıklama yapabilirsiniz, ancak hata ayıklama için masaüstünüzde bir öykünücü kullanmak genellikle daha kolay olur.

- C++ iOS geliştirme araçları, iOS platformunu hedefleyen C++ kodu oluşturmak için gereklidir.

> [!NOTE]
> Visual Studio 2015 kullanıyorsanız bkz. [ınstall çoklu platform mobil uygulama geliştirme için Visual C++ (Visual studio 2015)](install-visual-cpp-for-cross-platform-mobile-development.md?view=msvc-140&preserve-view=true)

### <a name="install-the-mobile-development-with-c-workload"></a>C++ iş yüküyle mobil geliştirme 'yi yükler

1. **Başlangıç** menüsünden **Visual Studio yükleyicisi** çalıştırın.

1. Visual Studio 'Yu zaten yüklediyseniz, değiştirmek istediğiniz Visual Studio 'nun yüklü sürümü için **Değiştir** düğmesini seçin. Aksi halde, Visual Studio 'Yu yüklemek için **Install** ' ı seçin.

1. **Iş yükleri** sekmesi seçili olduğunda, aşağı kaydırın ve Visual Studio yükleyicisi C++ iş yüküne **sahip mobil geliştirmeyi** seçin. Bu iş yükü seçildiğinde, C++ geliştirmesi için gereken diğer bileşenler de seçilidir. Aynı anda yüklemek için diğer iş yüklerini ve ayrı bileşenleri de seçebilirsiniz. UWP 'yi de hedefleyen platformlar arası kod oluşturmak için **Evrensel Windows platformu geliştirme** iş yükünü seçin.

1. **Yükleme ayrıntıları** bölmesinde, **C++ ile mobil geliştirme**' ı genişletin. **Isteğe bağlı** bölümünde, NDK, Google Android Emulator, Intel Hardware Accelerated Execution Manager ve IncrediBuild Build Acceleration aracının ek sürümlerini seçebilirsiniz.

1. Varsayılan olarak, bir veya daha fazla Android SDK Kurulum bileşeni iş yüküne dahildir. Android SDK ek sürümleri mevcuttur. Yüklemenize bir tane eklemek için, **tek tek bileşenler** sekmesini seçin, sonra seçiminizi yapmak için SDK 'lar **, kitaplıklar ve çerçeveler** bölümüne gidin.

1. C++ iş yüküne ve diğer seçili iş yüklerinize ve isteğe bağlı bileşenlere **sahip mobil geliştirmeyi** yüklemek için **Değiştir** veya **yüklensin** düğmesini seçin.

   Yükleme tamamlandığında, yükleyiciyi kapatın ve bilgisayarınızı yeniden başlatın. Üçüncü taraf bileşenleri için bazı kurulum eylemleri, bilgisayar yeniden başlatılana kadar etkili olmayacaktır.

   > [!IMPORTANT]
   > Her şeyin doğru şekilde yüklendiğinden emin olmak için yeniden başlatmanız gerekir.

1. Visual Studio'yu açın.

## <a name="install-tools-for-ios"></a>İOS için araçları yükler

İOS kodu düzenlemek, hatalarını ayıklamak ve iOS Benzeticisinde dağıtmak için Visual Studio 'Yu kullanabilirsiniz. Ya da bir iOS cihazına. Lisanslama kısıtlamaları nedeniyle, kod bir Mac üzerinde uzaktan oluşturulmalıdır. Visual Studio kullanarak iOS uygulamaları derlemek ve çalıştırmak için, önce Mac 'inizde uzak aracıyı ayarlayın ve yapılandırın. Ayrıntılı yükleme yönergeleri, Önkoşullar ve yapılandırma seçenekleri için bkz. [iOS kullanarak derlemek için araçları yükleme ve yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md). İOS için derleme yapıyorsanız, bu adımı atlayabilirsiniz.

## <a name="install-or-update-dependencies-manually"></a>Bağımlılıkları el ile yükler veya güncelleştirir

C++ iş yüküne (veya Visual Studio 2015 ' de Visual C++ Mobile Development seçeneği) **mobil geliştirme** 'yı yüklerken tüm üçüncü taraf bağımlılıklarını yüklemenize gerek yoktur. [Araçları yükledikten](#install-the-tools)sonra bu adımları kullanarak bunları daha sonra yükleyemezsiniz. Visual Studio Yükleyicisi, en son üçüncü taraf bileşenlerini yüklemek için düzenli olarak güncelleştirilir. Güncelleştirilmiş SDK 'Ları ve NDKs 'leri yüklemek için bunu kullanın. Ayrıca, bunları Visual Studio 'dan bağımsız olarak yükleyebilir veya güncelleştirebilirsiniz.

SDK 'yı güncelleştirmek için SDK Manager uygulamasını Android SDK dizininde yeniden çalıştırabilirsiniz. Ve isteğe bağlı araçları ve ek API düzeylerini yüklemek için. SDK Yöneticisi uygulamasını çalıştırmak için **yönetici olarak çalıştır** kullanmadığınız sürece güncelleştirmeler yüklenemeyebilir. Android uygulaması oluşturma sorunları yaşıyorsanız, yüklü SDK 'larınıza yönelik güncelleştirmeler için SDK Yöneticisi ' ne bakın.

Android SDK öykünücülerini kullanmak için donanım hızlandırmayı ayarlamanız gerekebilir. Daha fazla bilgi için bkz. [öykünücü performansı Için donanım hızlandırma (Hyper-V & HAXM)](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin).

Çoğu durumda, Visual Studio yüklediğiniz üçüncü taraf yazılım için konfigürasyonları algılayabilir. İç ortam değişkenlerinde yükleme yollarını korur. Visual Studio IDE 'de bu platformlar arası geliştirme araçlarının varsayılan yollarını geçersiz kılabilirsiniz.

### <a name="to-set-the-paths-for-third-party-tools"></a>Üçüncü taraf araçların yollarını ayarlamak için

1. Visual Studio menü çubuğunda **Araçlar**  >  **Seçenekler**' i seçin.

1. **Seçenekler** iletişim kutusunda **platformlar arası**  >  **C++**  >  **Android**' i seçin.

   ![Android araç yolu seçenekleri](../cross-platform/media/cppmdd-options-android.png "Android araç yolu seçenekleri")

1. Bir araç tarafından kullanılan yolu değiştirmek için yolun yanındaki onay kutusunu işaretleyin ve metin kutusunda klasör yolunu düzenleyin. Klasörü seçmek için bir **Konum Seç** iletişim kutusunu açmak için de (**...**) düğmesini kullanabilirsiniz.

1. Özel araç klasörü konumlarını kaydetmek için **Tamam ' ı** seçin.

## <a name="see-also"></a>Ayrıca bkz.

[İOS kullanarak derlemek için Araçlar yükleyip yapılandırma](install-and-configure-tools-to-build-using-ios.md)\
[Platformlar arası mobil Visual C++](https://visualstudio.microsoft.com/vs/features/cplusplus-mdd/)
