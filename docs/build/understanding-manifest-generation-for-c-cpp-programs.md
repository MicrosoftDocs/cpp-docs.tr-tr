---
title: C/C++ programları bildirim üretimini anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb6a65c718b88e4072c0ddad19411bb8ea4ddcff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ Programları Bildirim Üretimini Anlama
A [bildirim](http://msdn.microsoft.com/library/aa375365) harici bir XML dosyası veya bir kaynak olabilir bir XML belgesi bir uygulama veya bir derleme katıştırılır. Bildirimi bir [yalıtılmış uygulama](http://msdn.microsoft.com/library/aa375190) adları ve paylaşılan yan yana derlemeler için uygulaması bağlamak çalışma zamanında sürümlerini yönetmek için kullanılır. Yan yana derleme bildirimi bağımlılıklarını adları, sürüm, kaynakları ve diğer derlemelerden belirtir.  
  
 Yalıtılmış bir uygulama veya bir yan yana derleme bildirimi oluşturmanın iki yolu vardır. İlk olarak, yazarın derlemenin kurallara ve adlandırma gereksinimlerini bildirim dosyasını el ile oluşturabilirsiniz. Visual C++ derlemeleri CRT, MFC, ATL veya diğerleri gibi yalnızca bir program bağımlı olması durumunda, alternatif olarak, daha sonra bir bildirim otomatik olarak bağlayıcı tarafından oluşturulabilir.  
  
 Visual C++ kitaplıkları üstbilgileri derleme bilgilerini içeren ve kitaplıkları uygulama kodunda eklendiğinde bu derleme bilgilerini bağlayıcı tarafından son ikili yönelik bir bildirim oluşturmak için kullanılır. Bağlayıcı ikili içinde bildirim dosyası katıştırmak değildir ve yalnızca bildirim dış dosyası olarak oluşturulmasına neden olabilir. Harici dosya olarak bir bildirime sahip tüm senaryoları için çalışmayabilir. Örneğin, özel derlemeler bildirimleri katıştırılmış önerilir. Nmake kodu oluşturmak için kullananlar gibi komut satırı derlemelerde bildirim aracını kullanarak bir bildirim katıştırılabilen; Daha fazla bilgi için bkz: [bildirim oluşturma komut satırında](../build/manifest-generation-at-the-command-line.md). Oluştururken [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], bir bildirim için bildirim aracı özellik ayarlayarak katıştırılabilen **proje özelliklerini** iletişim; bkz: [Visual Studio'da bildirim oluşturma](../build/manifest-generation-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar ve yan yana derlemeler kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)