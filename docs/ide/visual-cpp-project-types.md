---
title: "Visual C++ proje türleri | Microsoft Docs"
ms.custom: 
ms.date: 10/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- programs [C++], projects
- project templates [Visual Studio], C++
- TODO comments [C++]
- projects [C++], types
- templates [C++], projects
- applications [C++], projects
- Visual C++ projects, types
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a837aa04b0e0c2b8d3d9f5cfd48181a9ea23b346
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-project-types"></a>Visual C++ Proje Türleri

Temel program yapısı, menüler, araç çubukları, simgeler, başvuruları oluşturmak için bir proje şablonu kullanın ve `#include` oluşturmak istediğiniz proje türü için uygun olan deyimleri. Visual Studio, Visual C++ proje şablonları çeşitli türlerde içerir ve böylece oluştururken projelerinizi özelleştirebilirsiniz sihirbazları birçoğu için sağlar. Bir proje oluşturmadan hemen sonra bunu oluşturmak ve uygulamayı çalıştırın; Uygulamanızı geliştirirken aralıklı oluşturmak iyi bir uygulamadır.

Bir proje oluşturmak için bir şablon kullanmanız gerekmez, ancak çoğu durumda, sıfırdan oluşturmak yerine sağlanan proje dosyalarını ve yapısını değiştirmek daha kolay olduğundan Bunu yapmak için daha verimli olur.  
  
> [!NOTE]
> C dili proje C++ proje şablonları kullanarak oluşturabilirsiniz. Oluşturulan projede bir .cpp şekilde değiştirin ve dosya adı uzantısına sahip dosyalar bulun. c. Ardından **proje özelliklerini** sayfasında projesi (için çözüm) için **yapılandırma özellikleri**, **C/C++** seçip **Gelişmiş**. Değişiklik **derleme olarak** ayarını **C kodu olarak derleme (/ TC)**.

## <a name="project-templates"></a>Proje şablonları

Visual Studio'da bulunan proje şablonları, ürün sürümü ve yüklemiş olduğunuz iş yükleri bağlıdır. C++ yüküyle masaüstü geliştirme yüklediyseniz, Visual Studio bu Visual C++ proje şablonları vardır.

### <a name="windows-desktop"></a>Windows Masaüstü

|Proje şablonu|Açıklama|  
|----------------------|-----------------------------| 
|[Windows konsol uygulaması](../windows/creating-a-console-application.md)|Bir Windows konsol uygulaması oluşturmaya yönelik bir proje.|
|[Windows masaüstü uygulaması](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Windows Masaüstü (Win32) uygulaması oluşturmaya yönelik bir proje.|
|[Dinamik bağlantı kitaplığı](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|Bir dinamik bağlantı kitaplığı (DLL) oluşturmak için bir proje.|
|[Statik kitaplığı](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Bir statik kitaplık (LIB) oluşturmak için bir proje.|
|Windows Masaüstü Sihirbazı|Windows Masaüstü uygulamaları ve kitaplıkları ek seçeneklerle oluşturmak için bir sihirbaz.|

### <a name="general"></a>Genel

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|Boş Proje|Bir uygulama, kitaplığı veya DLL oluşturmak için boş bir proje. Herhangi bir kod veya gerekli kaynakları eklemeniz gerekir.|
|[Derleme görevleri dosyası projesi](../ide/creating-a-makefile-project.md)|Bir dış kullanmak için bir proje sistem oluşturun.|
|Öğeleri proje paylaşılan|Birden çok proje arasında dosya paylaşımı için kullanılan bir proje.|

### <a name="atl"></a>ATL

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[ATL Proje](../atl/reference/creating-an-atl-project.md)|Etkin Şablon Kütüphanesi kullanan bir proje.|

### <a name="test"></a>Test

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[Yerel birim testi projesi](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|Yerel C++ birim testleri içeren bir projesi.|

### <a name="mfc"></a>MFC

Visual Studio yüklemenizin bileşenine MFC ve ATL desteği eklerseniz, bu proje şablonları için Visual Studio eklenir.

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[MFC uygulaması](../mfc/reference/creating-an-mfc-application.md)|Microsoft Foundation Class (MFC) kitaplığı kullanan bir uygulama oluşturmaya yönelik bir proje.|
|[MFC ActiveX denetimi](../mfc/reference/creating-an-mfc-activex-control.md)|MFC kitaplığını kullanan bir ActiveX denetimi oluşturmak için bir proje.|
|[MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md)|MFC kitaplığını kullanan bir dinamik bağlantı kitaplığı oluşturmak için bir proje.|

### <a name="windows-universal-apps"></a>Windows Evrensel uygulamaları

Visual Studio yüklemenizin C++ Evrensel Windows platformu araçları bileşeni eklerseniz, bu proje şablonları için Visual Studio eklenir.

C++'ta Windows Evrensel uygulamaları genel bakış için bkz: [Evrensel Windows uygulamaları (C++)](../windows/universal-windows-apps-cpp.md).

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|Boş Uygulama|Bir proje için önceden tanımlanmış denetimleri veya düzeni bulunmayan bir tek sayfalı Evrensel Windows Platformu (UWP) uygulaması.|
|DirectX 11 uygulama|DirectX 11 kullanan bir evrensel Windows Platform uygulaması için bir proje.|
|DirectX 12 uygulama|DirectX 12 kullanan bir evrensel Windows Platform uygulaması için bir proje.|
|DirectX 11 ve XAML uygulama|DirectX 11 ve XAML kullanan bir evrensel Windows Platform uygulaması için bir proje.|
|Birim testi uygulama|Evrensel Windows Platformu (UWP) uygulamaları için bir birim testi uygulama oluşturmak için bir proje.|
|DLL|Bir proje bir evrensel Windows platformu uygulamasında veya çalışma zamanı bileşeni tarafından kullanılan yerel bir dinamik bağlantı kitaplığının (DLL).|
|Statik kitaplığı|Bir proje için evrensel Windows platformu uygulamasında veya çalışma zamanı bileşeni tarafından kullanılan yerel statik bağlantı kitaplığı (LIB).|
|Windows Çalışma Zamanı Bileşeni|Uygulama yazıldığı programlama diline bakılmaksızın bir evrensel Windows Platform uygulaması tarafından kullanılan bir Windows çalışma zamanı bileşeni için bir proje.|
|Windows Uygulama paketleme projesi|Bir UWP paket oluşturan bir proje dışarıdan yüklenen veya Microsoft Store aracılığıyla dağıtılmış bir masaüstü uygulaması sağlar.|

## <a name="todo-comments"></a>Yapılacaklar açıklamaları

Bir proje şablonu tarafından oluşturulan dosyalar birçoğu, kendi kaynak kodunuz nerede sağlayabilir tanımlamanıza yardımcı olması için Yapılacaklar açıklamaları içerir. Kod ekleme hakkında daha fazla bilgi için bkz: [kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md) ve [kaynak dosyalarıyla çalışma](../windows/working-with-resource-files.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)   
