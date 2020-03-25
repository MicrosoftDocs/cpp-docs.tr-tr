---
title: CLR Projeleri için Oluşturulan Dosyalar
ms.date: 11/04/2016
helpviewer_keywords:
- Visual Studio C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
ms.openlocfilehash: 45295a3395f19d32dbf29948e1cbd15cd844adb4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169012"
---
# <a name="files-created-for-clr-projects"></a>CLR Projeleri için Oluşturulan Dosyalar

Projelerinizi oluşturmak için görsel C++ Şablonlar kullandığınızda, kullandığınız şablona bağlı olarak birkaç dosya oluşturulur. Aşağıdaki tabloda, .NET Framework projeleri için proje şablonları tarafından oluşturulan tüm dosyalar listelenmektedir.

|Dosya adı|Dosya açıklaması|
|---------------|----------------------|
|AssemblyInfo. cpp|Projenin derleme meta verilerini değiştirmek için bilgi (yani, öznitelikler, dosyalar, kaynaklar, türler, sürüm oluşturma bilgileri, imzalama bilgileri vb.) içeren dosya. Daha fazla bilgi için bkz. [derleme kavramları](/dotnet/framework/app-domains/assembly-contents).|
|*ProjName*. asmx|XML Web hizmetinin işlevselliğini kapsülleyen yönetilen sınıflara başvuran bir metin dosyası.|
|*ProjName*. cpp|Ana kaynak dosya ve giriş noktası, Visual Studio 'nun sizin için oluşturduğu uygulamada yer alan bir uygulamadır. Project. dll dosyasını ve proje ad alanını tanımlar. Bu dosyada kendi kodunuzu girin.|
|*ProjName*. vsdisco|XML Web hizmetini tanımlayan diğer kaynakların bağlantılarını içeren bir XML dağıtım dosyası.|
|*ProjName*. h|Diğer üstbilgi dosyaları için tüm bildirimleri, genel sembolleri ve `#include` yönergelerini içeren proje için ana ekleme dosyası.|
|*ProjName*. sln|Projenizin tüm öğelerini tek bir çözümde düzenlemek için geliştirme ortamında kullanılan çözüm dosyası.|
|*ProjName*. suo|Geliştirme ortamı içinde kullanılan çözüm seçenekleri dosyası.|
|*ProjName*. vcxproj|Bu projeye özgü bilgileri depolayan geliştirme ortamı içinde kullanılan proje dosyası.|
|ReadMe. txt|Şablon tarafından oluşturulan gerçek dosya adlarını kullanarak projenizdeki her dosyayı açıklayan bir dosya.|
