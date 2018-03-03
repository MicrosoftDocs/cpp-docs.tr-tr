---
title: "C/C++ yalıtılmış uygulamaları ve yan yana derlemeleri | Microsoft Docs"
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
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5dec3b0db6d77cc11d0e2ccdc97fe54ab8e0624
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma
Visual C++ üzerinde fikrini tabanlı Windows istemci uygulamaları için bir dağıtım modeli destekler [yalıtılmış uygulamalar](http://msdn.microsoft.com/library/aa375190) ve [yan yana derlemeler](http://msdn.microsoft.com/library/ff951640). Varsayılan olarak, Visual C++ tüm yerel C/C++ uygulamaları kullanan olarak yalıtılmış uygulamalar derlemeler [bildirimleri](http://msdn.microsoft.com/library/aa375365) bağımlılıklarını Visual C++ kitaplıkları üzerinde açıklamak için.  
  
 C/C++ programları olarak yalıtılmış uygulamalar derleme avantajları bir aralığı gösterir. Örneğin, diğer C/C++ uygulamaları yüklediğinizde veya Visual C++ kitaplıkları kaldırdığınızda yalıtılmış bir uygulama etkilenmez. Yalıtılmış uygulamalar tarafından kullanılan visual C++ kitaplıkları hala uygulamanın yerel klasör içinde ya da yerel Derleme Önbelleği (WinSxS); yüklemesi tarafından dağıtılabilir Ancak, önceden dağıtılan uygulamaları kullanarak basit hale getirilebilir için Visual C++ kitaplıkları bakım bir [yayımcı yapılandırma dosyası](http://msdn.microsoft.com/library/aa375680). Yalıtılmış uygulama dağıtım modeli, belirli bir bilgisayarda çalışan C/C++ uygulamaları hala olasılığını sistem yöneticileri için açık bırakarak Visual C++ kitaplıkları, en son sürümünü kullandığınızdan emin olun kolaylaştırır ve uygulamaları kendi bağımlı DLL'ler için açık sürüm bağlamasının denetlemek için uygulama yazarları.  
  
 Bu bölümde, nasıl C/C++ uygulamanızı yalıtılmış bir uygulama olarak oluşturun ve bildirim kullanarak Visual C++ kitaplıkları bağlar olun anlatılmaktadır. Bu bölümdeki bilgiler, öncelikle yerel veya yönetilmeyen, Visual C++ uygulamaları için geçerlidir. Visual C++ ile yerleşik yerel uygulamalarını dağıtma hakkında daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)  
  
 [C/C++ Yalıtılmış Uygulamaları Derleme](../build/building-c-cpp-isolated-applications.md)  
  
 [C/C++ Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-side-by-side-assemblies.md)  
  
 [Nasıl Yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme](../build/how-to-build-registration-free-com-components.md)  
  
 [Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
 [C/C++ Programları Bildirim Üretimini Anlama](../build/understanding-manifest-generation-for-c-cpp-programs.md)  
  
 [C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Yalıtılmış uygulamalar ve yan yana derlemeler](http://msdn.microsoft.com/library/dd408052)  
  
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)