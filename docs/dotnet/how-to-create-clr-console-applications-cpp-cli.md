---
title: 'Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
ms.openlocfilehash: 610efc8b0780422fc89e3bf9708ba488fe7d1f47
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80080061"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)

Konsol uygulaması şablonunu, zaten temel proje başvuruları ve dosyaları olan bir konsol uygulaması projesi oluşturmak için kullanabilirsiniz.

Genellikle, bir konsol uygulaması tek başına yürütülebilir bir dosyaya derlenir ancak grafik kullanıcı arabirimine sahip değildir. Bir Kullanıcı konsol uygulamasını bir komut isteminde çalıştırır ve çalışan uygulamaya yönergeler vermek için komut istemi 'ni kullanır. Ayrıca, komut isteminde uygulama çıktı bilgilerini sağlar. Konsol uygulamasının immediacy, bir kullanıcı arabirimi uygulamaya gerek duymadan programlama tekniklerini öğrenmenin harika bir yolunu sunar.

Bir proje oluşturmak için konsol uygulaması şablonunu kullandığınızda, otomatik olarak bu başvuruları ve dosyaları ekler:

- Bu .NET Framework ad alanlarına başvurular:

   - <xref:System.AppDomainManager>— yaygın olarak kullanılan değerleri ve başvuru veri türlerini, olayları ve olay işleyicilerini, arabirimleri, öznitelikleri ve işleme özel durumlarını tanımlayan temel sınıfları ve temel sınıfları Içerir.

   - mscorlib — .NET Framework geliştirmeyi destekleyen derleme DLL 'SI.

- Kaynak dosyalar:

   - Konsol (. cpp dosyası) — ana kaynak dosya ve giriş noktası, yeni oluşturduğunuz uygulamaya göre yapılır. Project. dll dosyasını ve proje ad alanını tanımlar. Bu dosyada kendi kodunuzu girin.

   - AssemblyInfo. cpp — projenin derleme meta verilerini değiştirmek için kullanabileceğiniz öznitelikleri, dosyaları, kaynakları, türleri, sürüm oluşturma bilgilerini, imzalama bilgilerini ve benzerlerini Içerir. Daha fazla bilgi için bkz. [bütünleştirilmiş kod içeriği](/dotnet/framework/app-domains/assembly-contents).

   - Stdadfx. cpp — Win32. pch adlı önceden derlenmiş bir üstbilgi dosyası ve Stbafx. obj adlı önceden derlenmiş türler dosyası oluşturmak için kullanılır.

- Üst bilgi dosyaları:

   - Stdadfx. h — Win32. pch adlı önceden derlenmiş bir üstbilgi dosyası ve Stdadfx. obj adlı önceden derlenmiş türler dosyası oluşturmak için kullanılır.

   - Resource. h — App. RC için oluşturulan bir içerme dosyası.

- Kaynak dosyaları:

   - App. RC — bir programın kaynak betik dosyası.

   - App. ico — bir programın simge dosyası.

- ReadMe. txt — projedeki dosyaları açıklar.

## <a name="to-create-a-common-language-runtime-clr-console-app-project"></a>Ortak dil çalışma zamanı (CLR) konsol uygulaması projesi oluşturmak için

1. Menü çubuğunda **Dosya**, **Yeni**, **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **yüklü şablonlar**altında,  **C++ görsel** düğümünü seçin, **clr** düğümünü seçin ve konsol uygulaması şablonunu seçin.

1. **Ad** kutusuna uygulamanız için benzersiz bir ad girin.

   Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak bunlar gerekli değildir.

1. **Tamam** düğmesini seçin.

## <a name="see-also"></a>Ayrıca bkz.

[CLR projeleri](../build/reference/files-created-for-clr-projects.md)
