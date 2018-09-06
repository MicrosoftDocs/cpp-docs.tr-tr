---
title: Derleme özelleştirmeleri sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2821c851c5b4498250a78f33eb111dd5f20ae272
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895155"
---
# <a name="troubleshooting-build-customizations"></a>Derleme Özelleştirmeleri Sorunlarını Giderme

Özel derleme adımları veya olayları beklediğiniz gibi davrandığını değil, yanlış neler olduğunu anlamak yapabileceğiniz birkaç şey vardır.

- Özel derleme adımlarınızı oluşturmak dosyalarını çıktı bildirdiğiniz dosyaları eşleştiğinden emin olun.

- Özel derleme adımlarınızı girişleri herhangi bir dosya oluşturmak veya diğer bağımlılıkları derleme adımları (özel veya diğer) dosyaları projenize eklendiğinden emin olun. Ve özel derleme sonra adım bu dosyaları kullanmak araçları yürütmek emin olun.

- Özel derleme adımı gerçekten yaptığı görüntüleme, ekleme `@echo on` ilk komut olarak. Derleme adımlarını ve derleme olaylarını bir geçici .bat dosyasına yerleştirilebilir ve proje derlenirken çalıştırın. Bu nedenle, derleme etkinliğiniz denetlenirken hata oluştu ekleyebilir veya adım komutları oluşturun.

- Gerçekte ne yürütülen görmek için Ara dosyaları dizinindeki yapılandırma günlüğünü inceleyin. Yapı günlüğüne adını ve yolunu tarafından temsil edilen **MSBuild** makrosu ifade **$(ıntdir)\\$(MSBuildProjectName) .log**.

- Derleme günlüğünde bilgi varsayılan miktarından daha toplamak için proje ayarlarınızı değiştirin. Üzerinde **Araçları** menüsünü tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusu, tıklayın **projeler ve çözümler** düğümünü ve ardından **derleme ve çalıştırma** düğümü. Ardından **MSBuild projesi derleme günlük dosyası ayrıntısı** kutusunun **ayrıntılı**.

- Kullanmakta olduğunuz adı veya dizin makroları değerlerin herhangi dosya doğrulayın. Ayrı ayrı makroları echo veya ekleyebileceğiniz `copy %0 command.bat` , özel derleme adımı başlangıcına kadar hangi kopyalar command.bat özel derleme adımının komutları içeren tüm makro genişletilmiş.

- Özel derleme adımlarını çalıştırmayı ve derleme olayları ayrı ayrı davranışlarını denetlemek için.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)