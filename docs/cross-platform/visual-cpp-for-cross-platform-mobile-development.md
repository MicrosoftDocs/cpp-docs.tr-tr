---
title: C++ ile platformlar arası mobil geliştirme
ms.date: 11/14/2019
ms.assetid: 0bb872d6-981b-4c96-9143-fcec5336bf0d
ms.openlocfilehash: dd2ea678d7689fac60bcee3555772b87df06e31b
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78177544"
---
# <a name="cross-platform-mobile-development-with-c"></a>C++ ile platformlar arası mobil geliştirme

Visual Studio 'da bulunan C++ platformlar arası araçları kullanarak IOS, Android ve Windows cihazları için yerel uygulamalar oluşturabilirsiniz. **İle C++ mobil geliştirme** , Visual Studio yükleyicisinde sunulan bir iş yüküdür. Paylaşılan kitaplıkların ve yerel uygulamaların platformlar arası geliştirmesi için ihtiyacınız olan SDK 'Ları ve araçları yüklenir. Yüklendiğinde, iOS ve Android cihazlar ve platformlar C++ , Windows, Windows Mağazası ve Xbox üzerinde çalışan kod oluşturmak için kullanabilirsiniz.

Birden çok platform için kod yazmak genellikle sinir bozucu olur. İOS, Android ve Windows için birincil geliştirme dilleri ve araçları her platformda farklıdır. Ancak, tüm platformlar ' de C++kod yazmayı destekler. Platformlar arasında çekirdek kod yeniden kullanımını etkinleştirebileceğinden ortak paydası vardır. İçinde C++ yazılan yerel kod, ters mühendislik için hem daha fazla performans hem de dayanıklı olabilir. Kod yeniden kullanımı, birden çok platform için uygulama oluştururken hem zaman hem de efor tasarrufu sağlayabilir.

Platformlar arası C++ mobil geliştirme için kullanılan geliştirme birçok avantaj sunar:

- **Kolay yükleme.** Visual Studio yükleyicisi, Android ve iOS için uygulamalar veya kitaplıklar oluşturmak için gereken gerekli üçüncü taraf araçları ve SDK 'Ları alır ve kurar. Yapılandırma ve kurulum basit ve genellikle otomatiktir.

- **Güçlü ve tanıdık bir yapı ortamı.** Visual Studio şablonlarıyla kolayca paylaşılabilir platformlar arası çözümler ve projeler oluşturun. Tek bir ortak arabirim kullanarak tüm projelerin özelliklerini yönetin. Visual Studio düzenleyicisinde tüm kodunuzu düzenleyin ve kod tamamlama ve hata vurgulama için yerleşik platformlar arası IntelliSense 'den yararlanın.

- **Birleşik bir hata ayıklama deneyimi.** Visual Studio 'da birinci sınıf hata ayıklama araçlarını kullanarak tüm platformlarda kodu izleyin ve adım C++ adım Ilerleyin: Android cihazlar ve Öykünücüler, iOS simülatörleri ve cihazlar ve Windows ya da Windows Mağazası cihazları ve öykünücüleri.

## <a name="get-the-tools"></a>Araçları edinin

İle C++ mobil geliştirme, Visual Studio ile birlikte gelen, yüklenebilen bir iş yüküdür. Önkoşullar ve yükleme yönergeleri için bkz. [platformlar arası mobil geliştirmeyi C++yükleme ](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). İOS için kod oluşturmak üzere bir Mac bilgisayar ve bir Apple iOS Geliştirici hesabı da gerekir. Daha fazla bilgi için bkz. [iOS kullanarak derlemek için araçları yükleyip yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

## <a name="come-up-to-speed"></a>En hızlı şekilde katılın

Android veya iOS Geliştirme işleminden geliyorsa, kullanmaya başlama hakkında harika bir malzememiz vardır. Visual Studio, ifade ve uyumlu bir geliştirme ortamıdır. Nasıl kullanacağınızı öğrenmek için [Android Geliştiricileri için kullanmaya](/previous-versions/windows/apps/dn275875\(v=win.10\)) başlayın veya [iOS geliştiricileri için kullanmaya](/previous-versions/windows/apps/jj657966\(v=win.10\))başlayın. Bu makaleler, sizi Visual Studio 'ya ve Windows ve Windows Mağazası için platformlar arası uygulamalar geliştirmeniz için gereken kavramlara tanıtmaktadır. İOS ve Android için ilk platformlar arası uygulamanızı yazmaya başlamak için bkz. [Android ve iOS üzerinde OpenGL ES uygulaması oluşturma](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md).

C++ İş yüküyle mobil geliştirme, uygulamalarınıza başlamanıza yardımcı olacak çeşitli şablonlar içerir:

- Native-Activity uygulaması (Android)

  Android yerel etkinlik C++ projesi olarak tamamen bir OpenGL uygulaması oluşturur.

- OpenGLES uygulaması (Android, iOS)

  Hem Android yerel etkinlik uygulaması hem de bir iOS uygulaması oluşturmak için bir proje kümesiyle bir çözüm oluşturur. Bu uygulamalar, her uygulamada aynı dönen kübü çizmek için ortak C++ OpenGL ES kodu kullanılarak oluşturulan platforma özgü kitaplıkları kullanır.

- Paylaşılan kitaplık (Android, iOS)

  Paylaşılan bir projede ortak C++ kod kullanarak Android dinamik kitaplığı (. so) dosyası ve bir iOS statik kitaplık (. a) dosyası oluşturmak için projelerle bir çözüm oluşturur.

- Temel uygulama (Android, Ant)

  Yalnızca Java kaynak kodu ve Ant derleme sistemi kullanan bir Android "Hello, World" uygulama projesi oluşturur.

- Temel uygulama (Android, Gradle)

  Yalnızca Java kaynak kodu ve Gradle yapı sistemi kullanan bir Android "Hello, World" uygulama projesi oluşturur.

- Temel kitaplık (Android, Ant)

  Yalnızca Java kaynak kodu ve Ant derleme sistemi kullanan bir Android "Hello, World" kitaplık projesi oluşturur.

- Temel kitaplık (Android, Gradle)

  Yalnızca Java kaynak kodu ve Gradle yapı sistemi kullanan bir Android "Hello, World" kitaplık projesi oluşturur.

- Dinamik Paylaşılan kitaplık (Android)

  Kodu kullanarak C++ bir Android dinamik kitaplığı (. so) dosyası oluşturur.

- OpenGLES 2 uygulaması (iOS)

  OpenGL ES 2 iOS uygulaması oluşturmak için bir proje kümesiyle bir çözüm oluşturur. Uygulama, bir iOS uygulamasında dönen C++ kübü çizmek için BIR OpenGL ES kodu kitaplığı kullanır. Bu uygulama, kitaplıkların iOS uygulamanıza nasıl içeri aktarılacağını C++ görmek için iyi bir başlangıç noktasıdır.

- Statik kitaplık (Android)

  Android için statik kitaplık oluşturmak üzere bir proje oluşturur. Bir Android uygulamasında yalnızca bir dinamik kitaplık bağlayabilirsiniz, ancak istediğiniz sayıda statik kitaplığı bağlayabilirsiniz.

- Statik kitaplık (iOS)

  İOS için statik kitaplık oluşturmak üzere bir proje oluşturur.

- Makefile projesi (Android)

  Kendi Android derleme görevleri dosyası projeleriniz için bir proje sarmalayıcısı oluşturur.

## <a name="try-out-sample-code"></a>Örnek kodu deneyin

Windows, Android ve iOS uygulamalarında kullanabileceğiniz paylaşılan kod kitaplıklarının nasıl oluşturulacağını gösteren örnekleri indirin. Ayrıca, Android için tamamen yerel etkinlik uygulamaları oluşturma örneklerine bakın. Başlamak için bkz. [platformlar arası mobil geliştirme örnekleri](../cross-platform/cross-platform-mobile-development-examples.md).

## <a name="see-also"></a>Ayrıca bkz.

\ [platformlar arası mobil geliştirme C++ ](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)
[İOS\ kullanarak derlemek için Araçlar yükleyip yapılandırın](../cross-platform/install-and-configure-tools-to-build-using-ios.md)
[Android yerel etkinlik uygulaması oluşturma](../cross-platform/create-an-android-native-activity-app.md)\
[Android ve iOS\ bir OpenGL ES uygulaması oluşturma](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md)
[Platformlar arası mobil geliştirme örnekleri](../cross-platform/cross-platform-mobile-development-examples.md)
