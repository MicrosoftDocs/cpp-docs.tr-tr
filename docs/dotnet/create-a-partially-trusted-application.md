---
title: "Nasıl yapılır: kısmen güvenilir uygulama oluşturma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dfef7eacfa9da8c55155f6e7ce43dfdb79e67e91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Nasıl yapılır: CRT Kitaplık DLL'inden Bağımlılık Kaldırarak Kısmen Güvenilir Uygulama Oluşturma
Bu konu, Visual C++ kullanarak msvcm90.dll bağımlılık kaldırarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulacağını açıklar.  
  
 İle oluşturulmuş bir Visual C++ uygulaması **/CLR** C çalışma zamanı kitaplığı parçası olan msvcm90.dll üzerinde bir bağımlılığa sahip olur. Kısmi güven ortamında kullanılmak üzere uygulamanızı istediğinizde, CLR DLL belirli kod erişim güvenlik kurallarında zorlar. Bu nedenle, çünkü msvcm90.dll yerel kod içerir ve kod erişimi güvenlik ilkesi üzerinde zorlanamaz bu bağımlılığı kaldırmak gerekli olacaktır.  
  
 Uygulamanız herhangi bir işlevsellik C çalışma zamanı kitaplığı kullanmaz ve kodunuzdan bu kitaplığa bağımlılığı kaldırmak istiyorsanız kullanması gerekir **/NODEFAULTLIB:msvcmrt.lib** bağlayıcı seçeneği ve bağlantıyı ptrustm.lib veya ptrustmd.lib. Bu kitaplıklar başlatma ve bir uygulamanın başlatılmaması nesne dosyalarını içeren, özel durum sınıfları başlatma kodu tarafından kullanılan ve özel durum işleme kodunu yönetilir. Bu kitaplıklar birinde bağlama msvcm90.dll herhangi bir bağımlılığı kaldırır.  
  
> [!NOTE]
>  Derleme başlatılmaması sırasını ptrust kitaplıklarını kullanan uygulamalar için farklı olabilir. Normal uygulamalar için derlemeleri genellikle yüklü olan, ancak bu garanti edilmez ters sırada kaldırılır. Kısmi güven uygulamaları için derlemeleri genellikle yüklendikleri sırayla kaldırılır. Bu, ayrıca, garanti edilmez.  
  
### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Kısmen güvenilen oluşturmak için karışık (/ clr) uygulama  
  
1.  Msvcm90.dll bağımlılığı kaldırmak için bu kitaplığı kullanarak içermeyecek şekilde bağlayıcıya belirtmeniz gerekir **/NODEFAULTLIB:msvcmrt.lib** bağlayıcı seçeneği. Visual Studio geliştirme ortamı kullanarak bunu veya programlı olarak görmek hakkında bilgi için [/NODEFAULTLIB (kitaplıkları yoksay)](../build/reference/nodefaultlib-ignore-libraries.md).  
  
2.  Ptrustm kitaplıklarından birini bağlayıcı giriş bağımlılıkları ekleyin. Uygulamanızı yayımlama modunda oluşturuyorsanız ptrustm.lib kullanın. Hata ayıklama modu için ptrustmd.lib kullanın. Visual Studio geliştirme ortamı kullanarak bunu veya programlı olarak görmek hakkında bilgi için [. Bağlayıcı girişi dosyaları lib](../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md)   
 [Karışık derlemeler için kitaplık desteği](../dotnet/library-support-for-mixed-assemblies.md)   
 [/ Link (seçenekleri bağlayıcıya geçir)](../build/reference/link-pass-options-to-linker.md)   
