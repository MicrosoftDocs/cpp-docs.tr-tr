---
title: Derleme Özelleştirmeleri Sorunlarını Giderme
ms.date: 11/04/2016
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
ms.openlocfilehash: 7a45b449dc9c3c4c81add37bbac0813c81133203
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315254"
---
# <a name="troubleshooting-build-customizations"></a>Derleme Özelleştirmeleri Sorunlarını Giderme

Özel derleme adımlarınız veya olaylarınız beklediğiniz gibi davranmıyorsa, neyin yanlış gittiğini anlamak için yapabileceğiniz birkaç şey vardır.

- Özel derleme adımlarınızın üretmesindeki dosyaların, çıkış olarak bildirdiğiniz dosyalarla eşleştiğinden emin olun.

- Özel derleme adımlarınız, diğer derleme adımlarının girdileri veya bağımlılıkları olan herhangi bir dosya (özel veya başka türlü) üretemiyor, bu dosyaların projenize eklendiğinden emin olun. Ve bu dosyaları kullanan araçların özel derleme adımından sonra yürütülmesine dikkat edin.

- Özel derleme adımlarınızın gerçekten ne yaptığını göstermek için ilk komut olarak `@echo on` ekleyin. Derleme olayları ve derleme adımları geçici bir. bat dosyasına konur ve proje oluşturulduğunda çalıştırılır. Bu nedenle, derleme olaylarınıza veya yapı adım komutlarına hata denetimi ekleyebilirsiniz.

- Aslında yürütüldüğünü görmek için ara dosyalar dizinindeki Derleme günlüğünü inceleyin. Yapı günlüğünün yolu ve adı, **$ (IntDir\\) $ (MSBuildProjectName). log** **MSBuild** makro ifadesi tarafından temsil edilir.

- Proje ayarlarınızı, yapı günlüğündeki varsayılan bilgi miktarından daha fazlasını toplayacak şekilde değiştirin. **Tools** (Araçlar) menüsünde **Options**’a (Seçenekler) tıklayın. **Seçenekler** iletişim kutusunda, **Projeler ve çözümler** düğümüne tıklayın ve ardından **Oluştur ve Çalıştır** düğümüne tıklayın. Ardından, **MSBuild proje derleme günlük dosyası ayrıntı düzeyi** kutusunda, **ayrıntılı**' e tıklayın.

- Kullandığınız herhangi bir dosya adının veya dizin makrolarının değerlerini doğrulayın. Makroları ayrı ayrı yankı edebilir veya özel derleme adımınızın `copy %0 command.bat` başlangıcına ekleyebilirsiniz. Bu, özel derleme adımınızın komutlarını, tüm makrolar genişletilmiş olacak şekilde Command. bat ' a kopyalayacaktır.

- Davranışlarını denetlemek için özel yapı adımlarını çalıştırın ve olayları ayrı ayrı oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](understanding-custom-build-steps-and-build-events.md)
