---
description: 'Hakkında daha fazla bilgi edinin: özel derleme adımlarını ve derleme olaylarını anlama'
title: Özel Derleme Adımlarını ve Derleme Olaylarını Anlama
ms.date: 08/29/2019
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
ms.openlocfilehash: da7e9399a1502c3d7ddaccbfb10a4d2b71fb85cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277407"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Özel Derleme Adımlarını ve Derleme Olaylarını Anlama

Visual C++ geliştirme ortamının içinden, yapı işlemini özelleştirmenin üç temel yolu vardır:

- **Özel derleme adımları**

   Özel derleme adımı bir projeyle ilişkili derleme kuralıdır. Özel bir yapı adımı yürütmek için bir komut satırı, herhangi bir ek giriş veya çıkış dosyası ve görüntülenecek bir ileti belirtebilir. Daha fazla bilgi için bkz. [nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md).

- **Özel derleme araçları**

   Özel derleme aracı bir veya daha fazla dosya ile ilişkili bir yapı kuralıdır. Özel derleme adımı, giriş dosyalarını bir veya daha fazla çıktı dosyası ile sonuçlanan özel bir derleme aracına geçirebilir. Örneğin, bir MFC uygulamasındaki Yardım dosyaları özel bir yapı aracıyla oluşturulmuştur. Daha fazla bilgi için bkz. [nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md) ve [özel derleme araçları belirtme](specifying-custom-build-tools.md).

- **Derleme olayları**

   Derleme olayları, projenin yapısını özelleştirmenizi sağlar. Üç derleme olayı vardır: *oluşturma öncesi*, *ön bağlantı* ve *Derleme sonrası*. Yapı olayı, derleme sürecinde belirli bir zamanda gerçekleşecek bir eylem belirtmenize olanak tanır. Örneğin, projenin derlemeyi tamamladıktan sonra **regsvr32.exe** bir dosyayı kaydetmek için bir yapı olayı kullanabilirsiniz. Daha fazla bilgi için bkz. [derleme olaylarını belirtme](specifying-build-events.md).

[Derleme özelleştirmeleri sorunlarını giderme](troubleshooting-build-customizations.md) , özel derleme adımlarınızın ve derleme olaylarınızın beklenen şekilde çalışmasını sağlamanıza yardımcı olabilir.

Özel bir derleme adımının veya derleme olayının çıkış biçimi, aracın kullanılabilirliğini de artırabilir. Daha fazla bilgi için bkz. [özel derleme adımının veya derleme olayının çıktısını biçimlendirme](formatting-the-output-of-a-custom-build-step-or-build-event.md).

Bir çözümdeki her proje için, derleme olayları ve özel derleme adımları diğer derleme adımlarıyla birlikte aşağıdaki sırayla çalışır:

1. Oluşturma öncesi olay

2. Tek tek dosyalardaki özel derleme araçları

3. MIDL

4. Kaynak derleyicisi

5. C/C++ derleyicisi

6. Bağlama Öncesi olay

7. Bağlayıcı veya Kütüphaneian (uygun şekilde)

8. Bildirim Aracı

9. BSCMake

10. Projede özel derleme adımı

11. Oluşturma sonrası olay

`custom build step on the project`Ve `post-build event` diğer tüm derleme işlemlerinden sonra sırayla çalışır.

## <a name="in-this-section"></a>Bu bölümde

[Özel derleme araçlarını belirtin](specifying-custom-build-tools.md)<br/>
[Derleme olaylarını belirtme](specifying-build-events.md)<br/>
[Derleme özelleştirmeleri sorunlarını giderme](troubleshooting-build-customizations.md)<br/>
[Özel derleme adımının veya derleme olayının çıktısını biçimlendirme](formatting-the-output-of-a-custom-build-step-or-build-event.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio projeleri-C++](creating-and-managing-visual-cpp-projects.md)<br>
[Derleme komutları ve özellikleri için genel makrolar](reference/common-macros-for-build-commands-and-properties.md)
