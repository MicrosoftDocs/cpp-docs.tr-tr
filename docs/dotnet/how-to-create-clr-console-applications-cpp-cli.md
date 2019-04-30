---
title: 'Nasıl yapılır: CLR konsol uygulamaları oluşturma (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
ms.openlocfilehash: ba0fa81aa42f946dbaf005c00380573e44312c5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387486"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Nasıl yapılır: CLR konsol uygulamaları oluşturma (C++/CLI)

Konsol uygulaması şablonu, temel proje başvuruları ve dosyalarını zaten bir konsol uygulaması projesi oluşturmak için kullanabilirsiniz.

Genellikle, bir konsol uygulaması bir tek başına yürütülebilir dosyasına derlenir, ancak bir grafik kullanıcı arabirimi yok. Bir kullanıcı, bir komut isteminde konsol uygulaması çalışır ve sorunu yönergeleri çalıştırılan uygulama için komut istemine kullanır. Uygulamayı komut isteminde çıkış bilgi de sağlar. Bir konsol uygulamasının immediacy kullanıcı arabirimini uygulamak için kaygısı olmadan programlama teknikleri öğrenmek için harika bir yöntemdir kolaylaştırır.

Bir proje oluşturmak için konsol uygulaması şablonunu kullandığınızda, otomatik olarak bu başvuruları ve dosyalarını ekler:

- Bu .NET Framework ad alanlarına başvurular:

   - <xref:System.AppDomainManager>— Temel sınıfları ve yaygın olarak kullanılan değerleri ve başvuru veri türleri, olayları ve olay işleyicileri, arabirimler, öznitelikleri ve işleme özel durum tanımlayan temel sınıfları içerir.

   - mscorlib — derleme DLL, .NET Framework için geliştirmeyi destekler.

- Kaynak dosyaları:

   - Konsolu (.cpp dosyası) — yeni oluşturduğunuz uygulamayı ana kaynak dosya ve giriş noktası. Bu proje .dll dosyası ve proje ad alanı tanımlar. Bu dosyadaki kendi kodunu sağlayın.

   - AssemblyInfo.cpp—Contains öznitelikleri, dosyaları, kaynaklar, türleri, sürüm oluşturma bilgilerini, imza bilgilerini ve projenin derleme meta verilerini değiştirmek için kullanabileceğiniz benzeri. Daha fazla bilgi için [derleme içerikleri](/dotnet/framework/app-domains/assembly-contents).

   - Stdafx.cpp—Used Win32.pch adlı bir ön derlenmiş üstbilgi dosyası ve adlı StdAfx.obj önceden derlenmiş türler dosyası oluşturmak için.

- Üst bilgi dosyaları:

   - Stdafx.h—Used Win32.pch adlı bir ön derlenmiş üstbilgi dosyası ve adlı StdAfx.obj önceden derlenmiş türler dosyası oluşturmak için.

   - oluşturulan resource.h—A app.rc dosyası içerir.

- Kaynak dosyaları:

   - bir programın App.rc—the kaynak betik dosyası.

   - bir programın App.ico—the simge dosyası.

- ReadMe.txt—Describes projesindeki dosyalar.

## <a name="to-create-a-common-language-runtime-clr-console-app-project"></a>Ortak dil çalışma zamanı (CLR) konsol uygulaması projesi oluşturmak için

1. Menü çubuğunda, **dosya**, **yeni**, **proje**.

1. İçinde **yeni proje** iletişim kutusunun **yüklü şablonlar**seçin **Visual C++** düğümünü **CLR** düğümüne tıklayın ve ardından Konsol uygulaması şablonu.

1. İçinde **adı** kutusuna, uygulamanız için benzersiz bir ad girin.

   Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak gerekli değildir.

1. Seçin **Tamam** düğmesi.

## <a name="see-also"></a>Ayrıca bkz.

[CLR projeleri](../build/reference/files-created-for-clr-projects.md)

