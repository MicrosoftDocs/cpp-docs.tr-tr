---
title: Visual Studio'da bildirim oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f927e153c25b41b48b783281a36dd2705e42006
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205806"
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio'da Bildirim Oluşturma
Belirli bir proje için bir bildirim dosyası üretimi projede denetlenebilir **özellik sayfaları** iletişim. Üzerinde **yapılandırma özellikleri** sekmesinde **bağlayıcı**, ardından **bildirim dosyası**, ardından **oluşturma bildirimi**. Varsayılan olarak, bir bildirim dosyası oluşturmak için yeni projeler, proje özellikleri ayarlanır. Ancak kullanarak bir proje için bildirim oluşturulmasını devre dışı bırakmak mümkündür **oluşturma bildirimi** projenin özelliği. Bu özelliği ayarlandığında **Evet**, bu proje için bildirim oluşturulur. Aksi takdirde bağlayıcı bağımlılıkları uygulama kodu çözülürken derleme bilgilerini yoksayar ve bildirim üretmez.  
  
 Visual Studio'da derleme sistemi son ikili uygulama dosyasında katıştırılmış veya bir dış dosya oluşturulan bildirim sağlar. Bu davranış tarafından denetlenir **ekleme bildirimi** seçeneğini **proje özellikleri** iletişim. Bu özelliği ayarlamak için açık **bildirim aracında** düğümünü seçip **giriş ve çıkış**. Bildirim gömülü değilse, bir dış dosya oluşturulan ve son ikili ile aynı dizinde kaydedildi. Visual Studio, bildirim katıştırılır, aşağıdaki işlemi kullanarak son bildirimleri gömer:  
  
1.  Kaynak kodu için nesne dosyaları derlendikten sonra bağlayıcı bağımlı derleme bilgilerini toplar. Bağlayıcı, son ikili bağlarken, daha sonra son bildirim oluşturmak için kullanılan bir ara bildirimi oluşturur.  
  
2.  Bildirim ve bağlama Ara tamamladıktan sonra bildirim aracı son bildirim birleştirme ve dış dosya kaydetmek için yürütülür.  
  
3.  Proje yapı sistemi sonra bildirim aracı tarafından oluşturulan bildirim zaten ikili dosyada gömülü bildirimle daha farklı bilgi içerip içermediğini algılar.  
  
4.  İkili dosyada gömülü bildirimle bildirim aracı tarafından oluşturulan bildirimden farklı veya ikili dosyada gömülü bir bildirim içermiyor, Visual Studio bağlayıcı bir kez daha dış bildirim dosyası içinde bir ikili dosya olarak eklemek için hizmetinizde bir Kaynak.  
  
5.  İkili dosyada gömülü bildirimle bildirim aracı tarafından oluşturulan bildirim ile aynı olduğunda, derleme yapı adımlarda devam eder.  
  
 Metin kaynak olarak son ikili içinde bildirim katıştırılır ve son ikili açarak Visual Studio'da bir dosya olarak görüntülenebilir. Bildirim doğru kitaplıklara işaret ettiğinden emin olmak için açıklanan adımları izleyin. [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) veya açıklanan önerileri uygulayın [sorungiderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) bölümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: C/C++ uygulamasına bildirim katıştırma](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [Özel derlemeler hakkında](/windows/desktop/SbsCs/about-private-assemblies-)   
 [Bildirim aracı](/windows/desktop/SbsCs/mt-exe)   
 [C/C++ Programları Bildirim Üretimini Anlama](../build/understanding-manifest-generation-for-c-cpp-programs.md)