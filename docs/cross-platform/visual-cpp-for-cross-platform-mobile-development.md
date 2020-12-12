---
description: 'Daha fazla bilgi edinin: C++ ile platformlar arası mobil geliştirme'
title: C++ ile platformlar arası mobil geliştirme
ms.date: 11/14/2019
ms.assetid: 0bb872d6-981b-4c96-9143-fcec5336bf0d
ms.openlocfilehash: 98e7124ca8a687a2308a97eb11da80fc0c69483a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213240"
---
# <a name="cross-platform-mobile-development-with-c"></a>C++ ile platformlar arası mobil geliştirme

İOS, Android ve Windows cihazları için, Visual Studio 'da bulunan platformlar arası araçları kullanarak yerel C++ uygulamaları oluşturabilirsiniz. **C++ Ile mobil geliştirme** , Visual Studio yükleyicisinde sunulan bir iş yüküdür. Paylaşılan kitaplıkların ve yerel uygulamaların platformlar arası geliştirmesi için ihtiyacınız olan SDK 'Ları ve araçları yüklenir. Yüklendiğinde, iOS ve Android cihazlar ve platformlar, Windows, Windows Mağazası ve Xbox 'ta çalışan kod oluşturmak için C++ kullanabilirsiniz.

Birden çok platform için kod yazmak genellikle sinir bozucu olur. İOS, Android ve Windows için birincil geliştirme dilleri ve araçları her platformda farklıdır. Ancak, tüm platformlar C++ ' da kod yazmayı destekler. Platformlar arasında çekirdek kod yeniden kullanımını etkinleştirebileceğinden ortak paydası vardır. C++ dilinde yazılan yerel kod, ters mühendislik için hem daha fazla performansı hem de dayanıklı olabilir. Kod yeniden kullanımı, birden çok platform için uygulama oluştururken hem zaman hem de efor tasarrufu sağlayabilir.

Platformlar arası mobil geliştirme için C++ kullanarak geliştirme birçok avantaj sunar:

- **Kolay yükleme.** Visual Studio yükleyicisi, Android ve iOS için uygulamalar veya kitaplıklar oluşturmak için gereken gerekli üçüncü taraf araçları ve SDK 'Ları alır ve kurar. Yapılandırma ve kurulum basit ve genellikle otomatiktir.

- **Güçlü ve tanıdık bir yapı ortamı.** Visual Studio şablonlarıyla kolayca paylaşılabilir platformlar arası çözümler ve projeler oluşturun. Tek bir ortak arabirim kullanarak tüm projelerin özelliklerini yönetin. Visual Studio düzenleyicisinde tüm kodunuzu düzenleyin ve kod tamamlama ve hata vurgulama için yerleşik platformlar arası IntelliSense 'den yararlanın.

- **Birleşik bir hata ayıklama deneyimi.** Visual Studio 'da birinci sınıf hata ayıklama araçlarını kullanarak tüm platformlarda C++ kodunu izleyin ve adım adım ilerleyin: Android cihazlar ve Öykünücüler, iOS simülatörleri ve cihazlar ve Windows ya da Windows Mağazası cihazları ve öykünücüleri.

## <a name="get-the-tools"></a>Araçları edinme

C++ ile mobil geliştirme, Visual Studio ile birlikte gelen, yüklenebilen bir iş yüküdür. Önkoşullar ve yükleme yönergeleri için bkz. [C++ ile platformlar arası mobil geliştirmeyi yükleme](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). İOS için kod oluşturmak üzere bir Mac bilgisayar ve bir Apple iOS Geliştirici hesabı da gerekir. Daha fazla bilgi için bkz. [iOS kullanarak derlemek için araçları yükleyip yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

## <a name="come-up-to-speed"></a>En hızlı şekilde katılın

Android veya iOS Geliştirme işleminden geliyorsa, kullanmaya başlama hakkında harika bir malzememiz vardır. Visual Studio, ifade ve uyumlu bir geliştirme ortamıdır. Nasıl kullanacağınızı öğrenmek için [Android Geliştiricileri için kullanmaya](/previous-versions/windows/apps/dn275875\(v=win.10\)) başlayın veya [iOS geliştiricileri için kullanmaya](/previous-versions/windows/apps/jj657966\(v=win.10\))başlayın. Bu makaleler, sizi Visual Studio 'ya ve Windows ve Windows Mağazası için platformlar arası uygulamalar geliştirmeniz için gereken kavramlara tanıtmaktadır. İOS ve Android için ilk platformlar arası uygulamanızı yazmaya başlamak için bkz. [Android ve iOS üzerinde OpenGL ES uygulaması oluşturma](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md).

C++ iş yüküyle mobil geliştirme, uygulamalarınıza başlamanıza yardımcı olacak çeşitli şablonlar içerir:

- Native-Activity uygulaması (Android)

  Android yerel etkinlik projesi olarak tamamen C++ OpenGL uygulaması oluşturur.

- OpenGLES uygulaması (Android, iOS)

  Hem Android yerel etkinlik uygulaması hem de bir iOS uygulaması oluşturmak için bir proje kümesiyle bir çözüm oluşturur. Bu uygulamalar, her uygulamada aynı dönen kübü çizmek için ortak C++ OpenGL ES kodu kullanılarak oluşturulan platforma özel kitaplıkları kullanır.

- Paylaşılan kitaplık (Android, iOS)

  Paylaşılan bir projede ortak C++ kodunu kullanarak Android dinamik kitaplığı (. so) dosyası ve bir iOS statik kitaplık (. a) dosyası oluşturmak için projelerle bir çözüm oluşturur.

- Temel uygulama (Android, Ant)

  Yalnızca Java kaynak kodu ve Ant derleme sistemi kullanan bir Android "Hello, World" uygulama projesi oluşturur.

- Temel uygulama (Android, Gradle)

  Yalnızca Java kaynak kodu ve Gradle yapı sistemi kullanan bir Android "Hello, World" uygulama projesi oluşturur.

- Temel kitaplık (Android, Ant)

  Yalnızca Java kaynak kodu ve Ant derleme sistemi kullanan bir Android "Hello, World" kitaplık projesi oluşturur.

- Temel kitaplık (Android, Gradle)

  Yalnızca Java kaynak kodu ve Gradle yapı sistemi kullanan bir Android "Hello, World" kitaplık projesi oluşturur.

- Dinamik Paylaşılan kitaplık (Android)

  C++ kodunu kullanarak bir Android dinamik kitaplığı (. so) dosyası oluşturur.

- OpenGLES 2 uygulaması (iOS)

  OpenGL ES 2 iOS uygulaması oluşturmak için bir proje kümesiyle bir çözüm oluşturur. Uygulama, bir iOS uygulamasında dönen kübü çizmek için bir C++ OpenGL ES kodu kitaplığı kullanır. Bu uygulama, C++ kitaplıklarının iOS uygulamanıza nasıl içeri aktarılacağını görmek için iyi bir başlangıç noktasıdır.

- Statik kitaplık (Android)

  Android için statik kitaplık oluşturmak üzere bir proje oluşturur. Bir Android uygulamasında yalnızca bir dinamik kitaplık bağlayabilirsiniz, ancak istediğiniz sayıda statik kitaplığı bağlayabilirsiniz.

- Statik kitaplık (iOS)

  İOS için statik kitaplık oluşturmak üzere bir proje oluşturur.

- Makefile projesi (Android)

  Kendi Android derleme görevleri dosyası projeleriniz için bir proje sarmalayıcısı oluşturur.

## <a name="try-out-sample-code"></a>Örnek kodu deneyin

Windows, Android ve iOS uygulamalarında kullanabileceğiniz paylaşılan kod kitaplıklarının nasıl oluşturulacağını gösteren örnekleri indirin. Ayrıca, Android için tamamen yerel etkinlik uygulamaları oluşturma örneklerine bakın. Başlamak için bkz. [platformlar arası mobil geliştirme örnekleri](../cross-platform/cross-platform-mobile-development-examples.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ ile platformlar arası mobil geliştirme 'yi yükler](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)\
[İOS kullanarak derlemek için Araçlar yükleyip yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md)\
[Android yerel etkinlik uygulaması oluşturma](../cross-platform/create-an-android-native-activity-app.md)\
[Android ve iOS üzerinde OpenGL ES uygulaması oluşturma](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md)\
[Platformlar arası mobil geliştirme örnekleri](../cross-platform/cross-platform-mobile-development-examples.md)
