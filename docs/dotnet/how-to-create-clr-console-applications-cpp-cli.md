---
title: 'Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
ms.openlocfilehash: 86e5abe330b0edc514fed74a12188ab73e8bfdd8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368531"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)

Temel proje referansları ve dosyaları olan bir konsol uygulaması projesi oluşturmak için Konsol Uygulaması şablonu'nu kullanabilirsiniz.

Genellikle, bir konsol uygulaması tek başına çalıştırılabilir bir dosyada derlenir, ancak grafik kullanıcı arabirimi yoktur. Kullanıcı konsol uygulamasını komut isteminde çalıştırıyor ve çalışan uygulamaya yönergeler vermek için komut istemini kullanır. Ayrıca komut istemi, uygulama çıktı bilgileri sağlar. Bir konsol uygulamasının yakınlığı, bir kullanıcı arabirimi uygulamak için endişelenmeden programlama tekniklerini öğrenmek için harika bir yol yapar.

Bir proje oluşturmak için Konsol Uygulaması şablonu kullandığınızda, otomatik olarak bu başvuruları ve dosyaları ekler:

- Bu .NET Framework ad alanlarına yapılan atıflar:

  - <xref:System.AppDomainManager>—Yaygın olarak kullanılan değerleri ve başvuru veri türlerini, olayları ve olay işleyicilerini, arabirimleri, öznitelikleri ve işleme özel durumlarını tanımlayan temel sınıfları ve temel sınıfları içerir.

  - mscorlib—.NET Framework geliştirmeyi destekleyen derleme DLL.

- Kaynak dosyalar:

  - Konsol (.cpp dosyası)—Yeni oluşturduğunuz uygulamaya ana kaynak dosyası ve giriş noktası. Proje .dll dosyasını ve proje ad alanını tanımlar. Bu dosyada kendi kodunuzu girin.

  - AssemblyInfo.cpp—Projenin derleme meta verilerini değiştirmek için kullanabileceğiniz öznitelikleri, dosyaları, kaynakları, türleri, sürüm bilgilerini, bilgileri imzalamayı ve benzeri özellikleri içerir. Daha fazla bilgi için [Montaj İçeriği'ne](/dotnet/framework/app-domains/assembly-contents)bakın.

  - Stdafx.cpp—Win32.pch adında önceden derlenmiş bir üstbilgi dosyası ve StdAfx.obj adlı önceden derlenmiş bir tür dosyası oluşturmak için kullanılır.

- Üstbilgi dosyaları:

  - Stdafx.h—Win32.pch adında önceden derlenmiş bir üstbilgi dosyası ve StdAfx.obj adlı önceden derlenmiş bir tür dosyası oluşturmak için kullanılır.

  - resource.h—Oluşturulan app.rc için dosya içerir.

- Kaynak dosyaları:

  - app.rc—Bir programın kaynak komut dosyası dosyası dosyası.

  - app.ico—Bir programın simge dosyası.

- ReadMe.txt—Projedeki dosyaları açıklar.

## <a name="to-create-a-common-language-runtime-clr-console-app-project"></a>Ortak bir dil çalışma zamanı (CLR) konsol uygulaması projesi oluşturmak için

1. Menü çubuğunda **Dosya**, **Yeni**, **Proje'yi**seçin.

1. Yeni **Proje** iletişim kutusunda, **Yüklü Şablonlar** **altında, Visual C++** düğümünü seçin, **CLR** düğümünü seçin ve ardından Konsol Uygulaması şablonunu seçin.

1. **Ad** kutusuna, başvurunuz için benzersiz bir ad girin.

   Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak bunlar gerekli değildir.

1. **Tamam** düğmesini seçin.

## <a name="see-also"></a>Ayrıca bkz.

[CLR Projeleri](../build/reference/files-created-for-clr-projects.md)
