---
title: "C/C++ programları bildirim üretimini anlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 848b4b449fa2c9c8930a616b70a5b61cb28d8fbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ Programları Bildirim Üretimini Anlama
A [bildirim](http://msdn.microsoft.com/library/aa375365) harici bir XML dosyası veya bir kaynak olabilir bir XML belgesi bir uygulama veya bir derleme katıştırılır. Bildirimi bir [yalıtılmış uygulama](http://msdn.microsoft.com/library/aa375190) adları ve paylaşılan yan yana derlemeler için uygulaması bağlamak çalışma zamanında sürümlerini yönetmek için kullanılır. Yan yana derleme bildirimi bağımlılıklarını adları, sürüm, kaynakları ve diğer derlemelerden belirtir.  
  
 Yalıtılmış bir uygulama veya bir yan yana derleme bildirimi oluşturmanın iki yolu vardır. İlk olarak, yazarın derlemenin kurallara ve adlandırma gereksinimlerini bildirim dosyasını el ile oluşturabilirsiniz. Visual C++ derlemeleri CRT, MFC, ATL veya diğerleri gibi yalnızca bir program bağımlı olması durumunda, alternatif olarak, daha sonra bir bildirim otomatik olarak bağlayıcı tarafından oluşturulabilir.  
  
 Visual C++ kitaplıkları üstbilgileri derleme bilgilerini içeren ve kitaplıkları uygulama kodunda eklendiğinde bu derleme bilgilerini bağlayıcı tarafından son ikili yönelik bir bildirim oluşturmak için kullanılır. Bağlayıcı ikili içinde bildirim dosyası katıştırmak değildir ve yalnızca bildirim dış dosyası olarak oluşturulmasına neden olabilir. Harici dosya olarak bir bildirime sahip tüm senaryoları için çalışmayabilir. Örneğin, özel derlemeler bildirimleri katıştırılmış önerilir. Nmake kodu oluşturmak için kullananlar gibi komut satırı derlemelerde bildirim aracını kullanarak bir bildirim katıştırılabilen; Daha fazla bilgi için bkz: [bildirim oluşturma komut satırında](../build/manifest-generation-at-the-command-line.md). Oluştururken [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], bir bildirim için bildirim aracı özellik ayarlayarak katıştırılabilen **proje özelliklerini** iletişim; bkz: [Visual Studio'da bildirim oluşturma](../build/manifest-generation-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar ve yan yana derlemeler kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)