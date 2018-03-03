---
title: "Bildirim üretme Visual Studio'da | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d701d73103ee2c5ac72eb36d9919132f0578b1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio'da Bildirim Oluşturma
Bildirim dosyası oluşturma belirli bir projenin projede denetlenebilir **özellik sayfaları** iletişim. Üzerinde **yapılandırma özellikleri** sekmesini tıklatın, **bağlayıcı**, ardından **bildirim dosyası**, ardından **oluşturmak bildirim**. Varsayılan olarak, bir bildirim dosyası oluşturmak için yeni projeler proje özelliklerini ayarlanır. Bununla birlikte kullanarak bir proje için bildirim oluşturulmasını devre dışı bırakmak mümkündür **oluşturmak bildirim** projesinin özelliği. Bu özellik ayarlandığında **Evet**, bu proje için bildirim oluşturulur. Aksi takdirde bağlayıcı uygulama kodunun bağımlılıkları çözümlenirken derleme bilgilerini yoksayar ve bildirim oluşturmaz.  
  
 Visual Studio'da derleme sistem son ikili uygulama dosyasında katıştırılmış veya harici dosya olarak oluşturulan bildirim sağlar. Bu davranış tarafından denetlenen **katıştırmak bildirim** seçeneğini **proje özelliklerini** iletişim. Bu özelliği ayarlamak için açık **bildirim aracı** düğümünü, ardından **giriş ve çıkış**. Bildirim gömülü olmayan, harici dosya olarak oluşturulan ve son ikili olarak aynı dizinde kaydedilir. Bildirim eklendiyse, bu Visual Studio aşağıdaki işlemi kullanarak son bildirimleri katıştırır:  
  
1.  Nesne dosyaları için kaynak kodunu derlendikten sonra bağlayıcı bağımlı derleme bilgilerini toplar. Son ikili bağlama sırasında bağlayıcı daha sonra son bildirimi oluşturmak için kullanılan bir ara bildirimi oluşturur.  
  
2.  Bildirim ve bağlama Ara tamamlanmış olan sonra bildirim aracı son bildirim birleştirme ve harici dosya olarak kaydetmek için yürütülür.  
  
3.  Proje oluşturma sistemi sonra bildirim aracı tarafından oluşturulan bildirimi zaten ikili katıştırılmış bildirimi olandan farklı bilgiler içerip içermediğini algılar.  
  
4.  Bildirim aracı tarafından oluşturulan bildirimindeki ikili katıştırılmış bildirimi farklıdır veya ikili gömülü bir bildirim içermiyor, Visual Studio bağlayıcı bir kez daha binary olarak içinde dış bildirim dosyası katıştırmak için çağıracağı bir Kaynak.  
  
5.  İkili katıştırılmış bildirimi bildirim aracı tarafından oluşturulan bildirimi aynı olduğunda, derleme yapı adımlarla devam eder.  
  
 Bildirim metin kaynak olarak son ikili içine katıştırılır ve Visual Studio bir dosya olarak son ikili açarak görüntülenebilir. Bildirim doğru kitaplıklara işaret ettiğinden emin olmak için açıklanan adımları izleyin [bir Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) veya açıklanan önerileri uygulayın [sorungiderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) bölümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: C/C++ uygulamasına bildirim katıştırma](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [Özel derlemeler hakkında](http://msdn.microsoft.com/library/ff951638)   
 [Bildirim aracı](http://msdn.microsoft.com/library/aa375649)   
 [C/C++ Programları Bildirim Üretimini Anlama](../build/understanding-manifest-generation-for-c-cpp-programs.md)