---
title: Bir C++ derleme görevleri dosyası projesi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3be9c22302bc693c44293266ea49ca97fae54f82
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535062"
---
# <a name="creating-a-c-makefile-project"></a>Bir C++ derleme görevleri dosyası projesi oluşturma

A *derleme görevleri dosyası* derleme ve bağlama ilişkin yönergeleri içeren bir metin dosyasıdır (veya *derleme*) C++ kaynak kodu dosyaları kümesi. A *olun* program derleme görevleri dosyası okur ve bir derleyici, bağlayıcı ve büyük olasılıkla diğer programları yürütülebilir bir dosya olmak için çağırır. Microsoft'un *olun* program çağrılır **NMAKE**. (Varsayılan olarak visual Studio .vcsproj dosyalara bağlı MSBuild sistemi kullanır; bu tarafından oluşturulan **dosya | Yeni | Proje**.)

Mevcut bir derleme görevleri dosyası projesi varsa, kod ve/veya Visual Studio IDE içinde hata ayıklamak istiyorsanız bu seçeneğiniz vardır: 

- Visual Studio'da IDE, kodunuzu derlemek için mevcut derleme görevleri dosyası kullanan bir derleme görevleri dosyası projesi oluşturun. (, Yerel bir MSBuild projesi ile aldığınız tüm IDE özelliklerini yoktur.) Bkz: [makefile projesi oluşturmak için](#create_a_makefile_project) aşağıda.
- Kullanım **varolan kod dosyalarından yeni proje oluştur** kaynak kodunuzu yerel bir MSBuild projesi oluşturmak için Sihirbazı. Daha fazla bilgi için [nasıl yapılır: Varolan koddan C++ projesi oluşturma](how-to-create-a-cpp-project-from-existing-code.md). 
- **Visual Studio 2017 ve üzeri**: kullanım **klasörünü Aç** özelliğini bir derleme görevleri dosyası açın. Daha fazla bilgi için [Klasör Aç Visual C++ projelerinde](non-msbuild-projects.md).

## <a name="a-namecreateamakefileproject-to-create-a-makefile-project-with-the-makefile-project-template"></a><a name="create_a_makefile_project"> Derleme görevleri dosyası proje şablonuyla bir derleme görevleri dosyası projesi oluşturmak için

Visual Studio 2017 ve sonraki sürümlerinde, C++ masaüstü geliştirme iş yükü yüklendiğinde Makefile projesi şablonunu kullanılabilir. 

Komutlar ve ortam, derleme görevleri dosyası tarafından kullanılan belirtmek için sihirbazı izleyin. Ardından bu projeyi Visual Studio geliştirme ortamında, kodunuzu derlemek için de kullanabilirsiniz. 

Varsayılan olarak, derleme görevleri dosyası projesi hiçbir dosya Çözüm Gezgini'nde görüntüler. Derleme görevleri dosyası proje, projenin özellik sayfasına yansıyan derleme ayarlarını belirtir.

Projede belirttiğiniz çıktı dosyasının, derleme komut dosyasının oluşturduğu ad üzerinde hiçbir etkisi yoktur; yalnızca bir amaç belirtir. Derleme görevleri dosyası yine de derleme işlemini denetler ve yapı hedeflerini belirtir.

1. "Derleme görevleri dosyası" yazın Visual Studio başlangıç sayfasından **yeni proje** arama kutusu. Veya **yeni proje** iletişim kutusunda **Visual C++** > **genel** (Visual Studio 2015) veya **diğer** (görsel Studio 2017'de) ve ardından **derleme görevleri dosyası projesi** Proje Sihirbazı'nı açmak için şablonlar bölmesindeki.

1. İçinde [uygulama ayarları](../ide/application-settings-makefile-project-wizard.md) sayfasında, komut çıktısında, temizleme ve yeniden oluşturma bilgileri için hata ayıklama ve perakende derlemeleri sağlayın.

1. Tıklayın **son** sihirbazı kapatın ve yeni oluşturulan projeyi **Çözüm Gezgini**.

Özellik sayfasında projenin özelliklerini görüntüleyebilir ve düzenleyebilirsiniz. Bkz: [Visual C++ proje özelliklerini ayarlama](../ide/working-with-project-properties.md) özellik sayfasını görüntüleme hakkında bilgi.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyası Projesi Sihirbazı](../ide/makefile-project-wizard.md)<br/>
[Derleme Görevleri Dosyasındaki Özel Karakterler](../build/special-characters-in-a-makefile.md)<br/>
[Derleme Görevleri Dosyası İçeriği](../build/contents-of-a-makefile.md)<br/>
