---
description: 'Hakkında daha fazla bilgi edinin: CLR projeleri için oluşturulan dosyalar'
title: CLR Projeleri için Oluşturulan Dosyalar
ms.date: 11/04/2016
helpviewer_keywords:
- Visual Studio C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
ms.openlocfilehash: 14aa07d891a75307f119f33ace5c32dbb2aa18db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200533"
---
# <a name="files-created-for-clr-projects"></a>CLR Projeleri için Oluşturulan Dosyalar

Projelerinizi oluşturmak için Visual C++ Şablonlar kullandığınızda, kullandığınız şablona bağlı olarak birkaç dosya oluşturulur. Aşağıdaki tabloda, .NET Framework projeleri için proje şablonları tarafından oluşturulan tüm dosyalar listelenmektedir.

|Dosya adı|Dosya açıklaması|
|---------------|----------------------|
|AssemblyInfo. cpp|Projenin derleme meta verilerini değiştirmek için bilgi (yani, öznitelikler, dosyalar, kaynaklar, türler, sürüm oluşturma bilgileri, imzalama bilgileri vb.) içeren dosya. Daha fazla bilgi için bkz. [derleme kavramları](/dotnet/framework/app-domains/assembly-contents).|
|*ProjName*. asmx|XML Web hizmetinin işlevselliğini kapsülleyen yönetilen sınıflara başvuran bir metin dosyası.|
|*ProjName*. cpp|Ana kaynak dosya ve giriş noktası, Visual Studio 'nun sizin için oluşturduğu uygulamada yer alan bir uygulamadır. Project. dll dosyasını ve proje ad alanını tanımlar. Bu dosyada kendi kodunuzu girin.|
|*ProjName*. vsdisco|XML Web hizmetini tanımlayan diğer kaynakların bağlantılarını içeren bir XML dağıtım dosyası.|
|*ProjName*. h|Diğer üstbilgi dosyaları için tüm bildirimleri, genel sembolleri ve yönergeleri içeren proje için ana ekleme dosyası `#include` .|
|*ProjName*. sln|Projenizin tüm öğelerini tek bir çözümde düzenlemek için geliştirme ortamında kullanılan çözüm dosyası.|
|*ProjName*. suo|Geliştirme ortamı içinde kullanılan çözüm seçenekleri dosyası.|
|*ProjName*. vcxproj|Bu projeye özgü bilgileri depolayan geliştirme ortamı içinde kullanılan proje dosyası.|
|ReadMe.txt|Şablon tarafından oluşturulan gerçek dosya adlarını kullanarak projenizdeki her dosyayı açıklayan bir dosya.|
