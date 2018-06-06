---
title: CLR projeleri için oluşturulan dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d66c3f55164a743bc395dc5e9b48f8bcd57654
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33334671"
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