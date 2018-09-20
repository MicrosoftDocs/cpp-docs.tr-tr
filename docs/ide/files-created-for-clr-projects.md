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
ms.openlocfilehash: 3bd76a978c1c85969883b8222097f29f501fd960
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385358"
---
# <a name="files-created-for-clr-projects"></a>CLR Projeleri için Oluşturulan Dosyalar

Projelerinizi oluşturmak için Visual C++ şablonları kullandığınızda, kullandığınız hangi şablonuna bağlı olarak çeşitli dosyalar oluşturulur. Aşağıdaki tablo, .NET Framework projeleri için proje şablonları tarafından oluşturulan tüm dosyaları listeler.

|Dosya adı|Dosya açıklaması|
|---------------|----------------------|
|AssemblyInfo.cpp|Proje derleme meta verileri değiştirme (diğer bir deyişle, öznitelikleri, dosyaları, kaynaklar, türleri, sürüm oluşturma bilgilerini, imza bilgilerini ve benzeri) bilgilerini içeren dosya. Daha fazla bilgi için [derleme kavramları](/dotnet/framework/app-domains/assembly-contents).|
|*PROJNAME*.asmx|Bir metin dosyası başvuruları, XML Web hizmeti işlevi kapsülleyen sınıfları yönetilen.|
|*PROJNAME*.cpp|Ana kaynak dosya ve giriş sizin için oluşturulan Visual Studio uygulamaya gelin. Proje .dll dosyası ve proje ad alanı tanımlar. Bu dosyadaki kendi kodunu sağlayın.|
|*PROJNAME*.vsdisco|XML Web hizmeti açıklayan diğer kaynakların bağlantılarını içeren bir XML dağıtım dosyası.|
|*PROJNAME*.h|Tüm bildirimleri, genel simge içeren, proje için ana içerme dosyası ve `#include` yönergeleri için diğer üst bilgi dosyaları.|
|*PROJNAME*.sln|Geliştirme ortamında projenizin tüm öğeleri tek bir çözümde düzenlemek için kullanılan çözüm dosyası.|
|*PROJNAME*.suo|Çözüm seçenekleri geliştirme ortamında kullanılan dosya.|
|*PROJNAME*.vcxproj|Proje dosyası bu projeye özgü bilgileri depolayan geliştirme ortamında kullanılır.|
|ReadMe.txt|Şablon tarafından oluşturulan gerçek dosya adlarını kullanarak, projenizdeki her dosyasını tanımlayan bir dosya.|