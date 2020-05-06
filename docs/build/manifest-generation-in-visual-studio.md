---
title: Visual Studio'da Bildirim Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
ms.openlocfilehash: f055e3d16dfc0ea4320883210458ae10daebdc45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273371"
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio'da Bildirim Oluşturma

Belirli bir proje için bildirim dosyası oluşturma proje **Özellik sayfaları** iletişim kutusunda denetlenebilir. **Yapılandırma özellikleri** sekmesinde **bağlayıcı**, ardından **bildirim dosyası**ve **bildirim oluştur**' a tıklayın. Varsayılan olarak, yeni projelerin proje özellikleri bir bildirim dosyası oluşturmak üzere ayarlanır. Ancak, projenin bildirim **Oluştur** özelliğini kullanarak bir proje için bildirimin oluşturulmasını devre dışı bırakmak mümkündür. Bu özellik **Evet**olarak ayarlandığında, bu proje için bildirim oluşturulur. Aksi takdirde bağlayıcı, uygulama kodunun bağımlılıklarını çözümlerken derleme bilgilerini yoksayar ve bildirimi oluşturmaz.

Visual Studio 'daki derleme sistemi, bildirimin son ikili uygulama dosyasına gömülmesini veya harici bir dosya olarak oluşturulmasını sağlar. Bu davranış, **Proje özellikleri** Iletişim kutusunda **ekleme bildirimi** seçeneği tarafından denetlenir. Bu özelliği ayarlamak için, **bildirim aracı** düğümünü açın **ve giriş ve çıkış**' ı seçin. Bildirim katıştırılmadıysanız, dış dosya olarak oluşturulur ve son ikiliden aynı dizine kaydedilir. Bildirim katıştırılmışsa, Visual Studio aşağıdaki işlemi kullanarak son bildirimleri katıştırır:

1. Kaynak kodu nesne dosyalarına derlendikten sonra bağlayıcı, bağımlı derleme bilgilerini toplar. Son ikili bağlama sırasında bağlayıcı, daha sonra son bildirimi oluşturmak için kullanılan bir ara bildirim oluşturur.

1. Ara bildirim ve bağlama işlemi tamamlandıktan sonra, bildirim aracı son bildirimi birleştirmek ve bir dış dosya olarak kaydetmek için yürütülür.

1. Proje derleme sistemi daha sonra, bildirim aracı tarafından oluşturulan bildirimin ikili dosyada zaten eklenmiş olan bildirimden farklı bilgiler içerip içermediğini algılar.

1. İkiliye gömülü bildirim, bildirim aracı tarafından oluşturulan bildirimden farklıysa veya ikili bir katıştırılmış bildirim içermiyorsa, Visual Studio, dış bildirim dosyasını ikili dosyanın içine kaynak olarak eklemek için bir kez daha zaman bağlayıcı çağırır.

1. İkiliye gömülü olan bildirim, bildirim aracı tarafından oluşturulan bildirimle aynıysa, derleme sonraki derleme adımlarına devam edecektir.

Bildirim, son ikilinin içine metin kaynağı olarak katıştırılır ve Visual Studio 'da dosya olarak son ikiliyi açılarak görüntülenebilir. Bildirimin doğru kitaplıklara işaret ettiğini sağlamak için, [bir Visual C++ uygulamasının bağımlılıklarını anlama](../windows/understanding-the-dependencies-of-a-visual-cpp-application.md) bölümünde açıklanan adımları Izleyin veya [sorun giderme](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) bölümünde açıklanan önerileri izleyin.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Programları Bildirim Üretimini Anlama](understanding-manifest-generation-for-c-cpp-programs.md)
