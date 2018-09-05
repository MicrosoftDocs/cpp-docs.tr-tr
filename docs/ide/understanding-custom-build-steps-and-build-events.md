---
title: Özel derleme adımlarını ve derleme olaylarını anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 410737380f6cc7c5ad52f29953926b3b1c2e71b5
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678091"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Özel Derleme Adımlarını ve Derleme Olaylarını Anlama
Gelen Visual C++ geliştirme ortamında, yapı işleminizi özelleştirmek için üç temel yolu vardır:  
  
 **Özel derleme adımları**  
 Özel derleme adımı, projeyle ilişkili bir derleme kuralıdır. Özel derleme adımı yürütmek için herhangi bir ek giriş veya çıkış dosyalarını ve görüntülenecek bir ileti bir komut satırı belirtebilirsiniz. Daha fazla bilgi için [nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).  
  
 **Özel derleme araçları**  
 Özel derleme aracı, bir veya daha fazla dosya ile ilişkilendirilmiş bir derleme kuralıdır. Özel derleme adımı birinde sonuçları bir özel derleme aracı için giriş dosyaları geçirebilir veya daha fazla çıkış dosyaları. Örneğin, bir MFC uygulamasında Yardım dosyaları, özel derleme aracı ile oluşturulur. Daha fazla bilgi için [nasıl yapılır: özel derleme araçları ekleme'MSBuild projelerine](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) ve [belirterek özel derleme Araçları](../ide/specifying-custom-build-tools.md).  
  
 **Derleme olayları**  
 Derleme olayları, bir projenin derleme özelleştirmenize olanak sağlar. Üç derleme olaylarını vardır: *derleme öncesi*, *bağlama öncesi*, ve *derleme sonrası*. Bir derleme olayı oluşturma işleminde belirli bir zamanda gerçekleşmesi için bir eylem belirtmenize olanak sağlar. Örneğin, bir dosya ile kaydetmek için bir derleme olay kullanabilirsiniz **regsvr32.exe** Proje yapı tamamlandıktan sonra. Daha fazla bilgi için [derleme olayları belirtme](../ide/specifying-build-events.md).  
  
 [Derleme özelleştirmeleri sorunlarını giderme](../ide/troubleshooting-build-customizations.md) özel derleme adımlarınızı emin olun ve beklendiği gibi çalışmazsa olayları oluşturmanıza yardımcı olabilir.  
  
 Çıktı biçimine göre özel derleme adımı veya derleme olayının aracı kullanılabilirliği de artırabilir. Daha fazla bilgi için [özel derleme adımı veya derleme olayının çıktısını biçimlendirme](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).  
  
 Derleme olayları ve özel derleme adımları birlikte başka yapılandırma adımları aşağıdaki sırayla çalıştırın:  
  
1.  Derleme öncesi olay  
  
2.  Özel derleme araçlarını tek tek dosyalar  
  
3.  MIDL  
  
4.  Kaynak Derleyicisi  
  
5.  C/C++ derleyicisi  
  
6.  Bağlama Öncesi olay  
  
7.  Bağlayıcı veya Kitaplıkçı (hangisi uygunsa)  
  
8.  Bildirim aracı  
  
9. BSCMake  
  
10. Projeye özel derleme adımı  
  
11. Derleme sonrası olay  
  
 `custom build step on the project` Ve `post-build event` sırayla diğer tüm derledikten sonra çalışma bitiş işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da C++ projeleri derleme](../ide/building-cpp-projects-in-visual-studio.md)   
 [Genel Derleme Komutları ve Özellikler Makroları](../ide/common-macros-for-build-commands-and-properties.md)   
