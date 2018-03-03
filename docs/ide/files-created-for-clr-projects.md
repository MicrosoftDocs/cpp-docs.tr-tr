---
title: "CLR projeleri için oluşturulan dosyalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4abf5415e9b252a7cc92408fb273d226106fc16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="files-created-for-clr-projects"></a>CLR Projeleri için Oluşturulan Dosyalar
Projelerinizi oluşturmak için Visual C++ şablonları kullandığınızda, hangi şablonuna bağlı olarak kullandığınız birkaç dosyaları oluşturulur. Aşağıdaki tabloda, .NET Framework projeleri için proje şablonları tarafından oluşturulan tüm dosyaları listelenmektedir.  
  
|Dosya adı|Dosya açıklaması|  
|---------------|----------------------|  
|AssemblyInfo.cpp|Proje derleme meta verilerini değiştirme bilgilerini (diğer bir deyişle, öznitelikler, dosyaları, kaynaklar, türleri, sürüm bilgisini, imzalama bilgilerini, vb.) içeren dosya. Daha fazla bilgi için bkz: [derleme kavramları](/dotnet/framework/app-domains/assembly-contents).|  
|*PROJNAME*.asmx|Başvuruları XML Web hizmeti işlevselliğini kapsülleyen sınıfları yönetilen bir metin dosyası.|  
|*PROJNAME*.cpp|Ana kaynak dosya ve giriş için oluşturduğunuz, Visual Studio uygulamaya gelin. Proje .dll dosyasını ve proje ad alanını tanımlar. Bu dosyadaki kendi kodunuzu girin.|  
|*PROJNAME*.vsdisco|XML Web hizmetini tanımlayan diğer kaynakların bağlantılarını içeren bir XML dağıtım dosyası.|  
|*PROJNAME*.h|Tüm bildirimleri, genel simgeleri içerir, proje için ana içerme dosyası ve `#include` diğer üstbilgi dosyaları için yönergeleri.|  
|*PROJNAME*.sln|Geliştirme ortamında tek bir çözümde projenizin tüm öğelerini düzenlemek için kullanılan çözüm dosyası.|  
|*PROJNAME*.suo|Geliştirme ortamında kullanılan çözüm seçenekleri dosyası.|  
|*PROJNAME*.vcxproj|Bu projeye özel bilgileri depolar geliştirme ortamında kullanılan proje dosyası.|  
|ReadMe.txt|Şablon tarafından oluşturulan gerçek dosya adları kullanılarak projenizdeki her dosya açıklayan bir dosya.|