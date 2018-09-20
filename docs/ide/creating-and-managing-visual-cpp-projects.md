---
title: Visual C++ proje oluşturma ve yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17b608ec68e0c4456b8789a4891da355ec732d2a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423630"
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>Visual C++ MSBuild tabanlı projeler oluşturma ve yönetme

MSBuild Visual C++ için yerel derleme sistemi ve genellikle en iyi MFC veya ATL kitaplığı kullanan masaüstü uygulamaların yanı sıra UWP uygulamaları için kullanılacak sistem oluşturun. MSBuild Visual Studio IDE ve proje sistemi ile sıkı bir şekilde tümleştirilmiştir, ancak bunu ayrıca komut satırından kullanabilirsiniz. Visual Studio 2017'den itibaren Visual C++ destekler [CMake ve MSBuild olmayan diğer sistemlere Klasör Aç özelliği](non-msbuild-projects.md).

Program yanı sıra diğer yapılandırma ayarlarını, örneğin hedef Platformu (x 86, x64 veya ARM) ve mi oluşturuyorsunuz derlemek için gereken tüm dosyalara ve kaynaklara belirten, XML biçimi (.vcxproj) proje dosyasında bir MSBuild tabanlı proje sahip bir programın hata ayıklama sürümünü veya serbest bırakın. Bir proje (ya da çok sayıda proje) bulunan bir *çözüm*; Örneğin, bir çözüm birkaç Win32 DLL projesi ve bu DLL'leri kullanan tek bir Win32 konsol uygulaması içerebilir. Proje oluşturduğunuzda, MSBuild altyapısına proje dosyası kullanır ve yürütülebilir dosyayı ve/veya belirttiğiniz başka herhangi bir özel çıktı üretir.

Visual C++ projelerini seçerek oluşturabilirsiniz **dosya &#124; yeni &#124; proje**, Visual C++'ın sol bölmede seçili olduğundan emin olduktan ve sonra orta bölmedeki proje şablonları listesinden seçerek. Bir şablona tıkladığınızda, çoğu durumda, proje oluşturulmadan önce çeşitli proje özelliklerini ayarlamanıza olanak sağlayan bir Sihirbazı görünür. Görüntüleyebilir ve bu özellikleri daha sonra projenin özellik sayfalarındaki kullanarak değiştirme (**proje &#124; özellikleri**).

Ayrıca, yeni projeleri tarafından oluşturabilirsiniz:

- seçme **dosya &#124; yeni &#124; mevcut koddan proje** ve mevcut kaynak kodu dosyaları eklemek için istemleri izleyerek. Bu seçenek nispeten küçük ve basit projelerde en iyi 25 kaynak kodu dosyaları veya az değişiklikle veya hiç karmaşık bağımlılıklar belki de çalışır.

- derleme görevleri dosyası ile başlayan ve Genel sekmesinin altında derleme görevleri dosyası projesi şablonu seçin.

- boş bir proje oluşturma (altında **genel** sekme) ve Çözüm Gezgini'nde proje düğümüne sağ tıklayıp seçerek kaynak kodu dosyaları el ile ekleyerek **Ekle &#124; var olan öğe**.

- kullanarak [Win32 Uygulama Sihirbazı](../windows/win32-application-wizard.md).

## <a name="in-this-section"></a>Bu Bölümde

[Visual C++ Proje Türleri](../ide/visual-cpp-project-types.md)<br>
Visual C++'ta kullanılabilir olan MSBuild tabanlı proje türlerini açıklar.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)<br>
Çeşitli MSBuild proje türleri ile birlikte kullanılan dosya türü açıklar.

[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
Visual C++ projeleri oluşturmak için sihirbaz kullanma

[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)<br>
Özellik sayfaları ve özellik sayfaları proje ayarlarınızı belirtmek için nasıl kullanılacağını açıklar.

[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
Sınıfları, yöntemleri, değişkenler ve diğer öğeleri işlevselliği eklemek için projenize eklemeyi açıklar.

[Nasıl Yapılır: Derlemeler için Proje Çıktı Dosyalarını Düzenleme](../ide/how-to-organize-project-output-files-for-builds.md)<br>
Proje çıktı dosyalarını düzenleme açıklar.

## <a name="related-sections"></a>İlgili Bölümler

[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br>
Programınızın komut satırından veya Visual Studio'nun tümleşik geliştirme ortamından oluşturmayı açıklayan konulara bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio SDK](https://msdn.microsoft.com/vstudio/extend)
