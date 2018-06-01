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
ms.openlocfilehash: a50c0cf224104f720a73a4830405e7114cda74ed
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33338773"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Özel Derleme Adımlarını ve Derleme Olaylarını Anlama
Gelen Visual C++ geliştirme ortamında yapı işlemi özelleştirmek için üç temel yolu vardır:  
  
 **Özel derleme adımları**  
 Özel derleme adımı, projeyle ilişkili bir yapı kuralıdır. Özel derleme adımı yürütmek için herhangi bir ek giriş veya çıkış dosyaları ve görüntülenecek bir ileti bir komut satırını belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: MSBuild projelerine özel derleme bir adım ekleme](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).  
  
 **Özel derleme araçları**  
 Özel derleme aracı, bir veya daha fazla ile ilişkili bir yapı kuralıdır. Özel derleme adımı birinde sonuçları bir özel derleme aracı için giriş dosyaları geçirebilir veya daha fazla çıkış dosyaları. Örneğin, bir MFC uygulamasında Yardım dosyalarını özel derleme aracıyla oluşturulur. Daha fazla bilgi için bkz: [nasıl yapılır: özel derleme araçları ekleme'MSBuild projelerine](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) ve [özel derleme araçlarını belirtme](../ide/specifying-custom-build-tools.md).  
  
 **Derleme olayları**  
 Derleme olayları bir projenin yapı özelleştirmenize olanak tanır. Üç derleme olaylarını vardır: *oluşturma öncesi*, *bağlama öncesi*, ve *oluşturma sonrası*. Derleme olayının derleme sürecindeki belirli bir zamanda gerçekleşmesi için bir eylem belirtmenize olanak sağlar. Örneğin, bir dosyayı kaydetmek için yapı olay kullanabilirsiniz **regsvr32.exe** Proje yapı tamamlandıktan sonra. Daha fazla bilgi için bkz: [derleme olayları belirtme](../ide/specifying-build-events.md).  
  
 [Derleme özelleştirmeleri sorunlarını giderme](../ide/troubleshooting-build-customizations.md) özel derleme adımları emin olun ve beklendiği gibi çalışmazsa olayları oluşturmanıza yardımcı olabilir.  
  
 Özel bir çıktı biçimi adım oluşturabilir veya derleme olayının Ayrıca, aracı kullanılabilirliğini artırabilirsiniz. Daha fazla bilgi için bkz: [özel derleme adımı veya derleme olayının çıktısını biçimlendirme](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).  
  
 Derleme olayları ve özel derleme adımları diğer yapı adımlarını aşağıdaki sırada çalıştırın:  
  
1.  Oluşturma öncesi olay  
  
2.  Özel derleme araçlarını tek tek dosyalar  
  
3.  MIDL  
  
4.  Kaynak Derleyicisi  
  
5.  C/C++ derleyicisi  
  
6.  Bağlama Öncesi olay  
  
7.  Bağlayıcı veya kitaplığı (hangisi uygunsa)  
  
8.  Bildirim aracı  
  
9. BSCMake  
  
10. Projeye özel derleme adımı  
  
11. Oluşturma sonrası olay  
  
 `custom build step on the project` Ve `post-build event` sırayla diğer tüm yapı sonra çalıştırma bitiş işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da C++ projeleri derleme](../ide/building-cpp-projects-in-visual-studio.md)   
 [Derleme komutları ve özellikler için ortak makroları](../ide/common-macros-for-build-commands-and-properties.md)   
 [Aracı derleme sırası iletişim kutusu](http://msdn.microsoft.com/en-us/6204c5b1-7ce9-4948-9ff6-0268642ee14c)