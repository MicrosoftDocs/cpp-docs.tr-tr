---
title: Özel Derleme Adımlarını ve Derleme Olaylarını Anlama
ms.date: 11/04/2016
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
ms.openlocfilehash: 5bc402ad8999f1864c7e6b1155da3c68862dda97
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824086"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Özel Derleme Adımlarını ve Derleme Olaylarını Anlama

Gelen Visual C++ geliştirme ortamında, yapı işleminizi özelleştirmek için üç temel yolu vardır:

- **Özel derleme adımları**

   Özel derleme adımı, projeyle ilişkili bir derleme kuralıdır. Özel derleme adımı yürütmek için herhangi bir ek giriş veya çıkış dosyalarını ve görüntülenecek bir ileti bir komut satırı belirtebilirsiniz. Daha fazla bilgi için [nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md).

- **Özel derleme araçları**

   Özel derleme aracı, bir veya daha fazla dosya ile ilişkilendirilmiş bir derleme kuralıdır. Özel derleme adımı birinde sonuçları bir özel derleme aracı için giriş dosyaları geçirebilir veya daha fazla çıkış dosyaları. Örneğin, bir MFC uygulamasında Yardım dosyaları, özel derleme aracı ile oluşturulur. Daha fazla bilgi için [nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md) ve [derleme araçlarını belirtme özel](specifying-custom-build-tools.md).

- **Derleme olayları**

   Derleme olayları, bir projenin derleme özelleştirmenize olanak sağlar. Üç derleme olaylarını vardır: *derleme öncesi*, *bağlama öncesi*, ve *derleme sonrası*. Bir derleme olayı oluşturma işleminde belirli bir zamanda gerçekleşmesi için bir eylem belirtmenize olanak sağlar. Örneğin, bir dosya ile kaydetmek için bir derleme olay kullanabilirsiniz **regsvr32.exe** Proje yapı tamamlandıktan sonra. Daha fazla bilgi için [derleme olayları belirtme](specifying-build-events.md).

[Derleme özelleştirmeleri sorunlarını giderme](troubleshooting-build-customizations.md) özel derleme adımlarınızı emin olun ve beklendiği gibi çalışmazsa olayları oluşturmanıza yardımcı olabilir.

Çıktı biçimine göre özel derleme adımı veya derleme olayının aracı kullanılabilirliği de artırabilir. Daha fazla bilgi için [özel derleme adımı veya derleme olayının çıktısını biçimlendirme](formatting-the-output-of-a-custom-build-step-or-build-event.md).

Derleme olayları ve özel derleme adımları birlikte başka yapılandırma adımları aşağıdaki sırayla çalıştırın:

1. Derleme öncesi olay

2. Özel derleme araçlarını tek tek dosyalar

3. MIDL

4. Kaynak Derleyicisi

5. C/C++ derleyicisi

6. Bağlama Öncesi olay

7. Bağlayıcı veya Kitaplıkçı (hangisi uygunsa)

8. Bildirim aracı

9. BSCMake

10. Projeye özel derleme adımı

11. Derleme sonrası olay

`custom build step on the project` Ve `post-build event` sırayla diğer tüm derledikten sonra çalışma bitiş işler.

## <a name="in-this-section"></a>Bu bölümde

[Özel derleme araçlarını belirtme](specifying-custom-build-tools.md)<br/>
[Derleme olayları belirtme](specifying-build-events.md)<br/>
[Derleme özelleştirmeleri sorunlarını giderme](troubleshooting-build-customizations.md)<br/>
[Özel derleme adımının veya derleme olayının çıktısını biçimi](formatting-the-output-of-a-custom-build-step-or-build-event.md)<br/>

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio projeleri - C++](creating-and-managing-visual-cpp-projects.md)<br>
[Genel derleme komutları ve Özellikler makroları](reference/common-macros-for-build-commands-and-properties.md)
