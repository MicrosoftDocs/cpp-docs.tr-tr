---
title: Visual Studio'da Bildirim Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
ms.openlocfilehash: f055e3d16dfc0ea4320883210458ae10daebdc45
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781685"
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio'da Bildirim Oluşturma

Belirli bir proje için bir bildirim dosyası üretimi projede denetlenebilir **özellik sayfaları** iletişim. Üzerinde **yapılandırma özellikleri** sekmesinde **bağlayıcı**, ardından **bildirim dosyası**, ardından **oluşturma bildirimi**. Varsayılan olarak, bir bildirim dosyası oluşturmak için yeni projeler, proje özellikleri ayarlanır. Ancak kullanarak bir proje için bildirim oluşturulmasını devre dışı bırakmak mümkündür **oluşturma bildirimi** projenin özelliği. Bu özelliği ayarlandığında **Evet**, bu proje için bildirim oluşturulur. Aksi takdirde bağlayıcı bağımlılıkları uygulama kodu çözülürken derleme bilgilerini yoksayar ve bildirim üretmez.

Visual Studio'da derleme sistemi son ikili uygulama dosyasında katıştırılmış veya bir dış dosya oluşturulan bildirim sağlar. Bu davranış tarafından denetlenir **ekleme bildirimi** seçeneğini **proje özellikleri** iletişim. Bu özelliği ayarlamak için açık **bildirim aracında** düğümünü seçip **giriş ve çıkış**. Bildirim gömülü değilse, bir dış dosya oluşturulan ve son ikili ile aynı dizinde kaydedildi. Visual Studio, bildirim katıştırılır, aşağıdaki işlemi kullanarak son bildirimleri gömer:

1. Kaynak kodu için nesne dosyaları derlendikten sonra bağlayıcı bağımlı derleme bilgilerini toplar. Bağlayıcı, son ikili bağlarken, daha sonra son bildirim oluşturmak için kullanılan bir ara bildirimi oluşturur.

1. Bildirim ve bağlama Ara tamamladıktan sonra bildirim aracı son bildirim birleştirme ve dış dosya kaydetmek için yürütülür.

1. Proje yapı sistemi sonra bildirim aracı tarafından oluşturulan bildirim zaten ikili dosyada gömülü bildirimle daha farklı bilgi içerip içermediğini algılar.

1. İkili dosyada gömülü bildirimle bildirim aracı tarafından oluşturulan bildirimden farklı veya ikili dosyada gömülü bir bildirim içermiyor, Visual Studio bağlayıcı bir kez daha dış bildirim dosyası içinde bir ikili dosya olarak eklemek için hizmetinizde bir Kaynak.

1. İkili dosyada gömülü bildirimle bildirim aracı tarafından oluşturulan bildirim ile aynı olduğunda, derleme yapı adımlarda devam eder.

Metin kaynak olarak son ikili içinde bildirim katıştırılır ve son ikili açarak Visual Studio'da bir dosya olarak görüntülenebilir. Bildirim doğru kitaplıklara işaret ettiğinden emin olmak için açıklanan adımları izleyin. [Visual C++ uygulaması bağımlılıklarını anlama](../windows/understanding-the-dependencies-of-a-visual-cpp-application.md) veya açıklanan önerileri uygulayın [sorungiderme](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) bölümü.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Programları Bildirim Üretimini Anlama](understanding-manifest-generation-for-c-cpp-programs.md)
