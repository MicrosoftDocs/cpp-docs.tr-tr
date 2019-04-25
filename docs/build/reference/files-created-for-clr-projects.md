---
title: CLR Projeleri için Oluşturulan Dosyalar
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
ms.openlocfilehash: 8c3e4b4187e507f7e52f8764b546f85258902879
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271049"
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