---
title: Visual C++ Proje Türleri
ms.date: 11/29/2018
helpviewer_keywords:
- programs [C++], projects
- project templates [Visual Studio], C++
- TODO comments [C++]
- projects [C++], types
- templates [C++], projects
- applications [C++], projects
- Visual C++ projects, types
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
ms.openlocfilehash: cac194ed2c830541711161dc139a42ed0529340f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823654"
---
# <a name="c-project-templates"></a>C++ proje şablonları

Kaynak kodu dosyaları, derleyici seçenekleri, menüler, araç çubukları, simgeler, başvurular, Visual Studio Proje şablonları oluşturmak ve `#include` oluşturmak istediğiniz proje türü için uygun olan deyimleri. Visual Studio çeşitli Visual C++ proje şablonları içerir ve oluştururken projelerinizi özelleştirebilmeniz için sihirbazları kaç tanesinin sağlar. Hemen bir proje oluşturduğunuzda, derleyin ve uygulamayı çalıştırın; Uygulamanızı geliştirirken, aralıklı olarak oluşturmak için iyi bir uygulamadır.

> [!NOTE]
> C++ proje şablonlarını kullanarak bir C dili projesi oluşturabilirsiniz. Oluşturulan proje bir .cpp olarak değiştirin ve dosya adı uzantısına sahip dosyaları bulun. c. Ardından **proje özellikleri** sayfasında projenin (için çözüm) **yapılandırma özellikleri**, **C/C++** seçip **Gelişmiş**. Değişiklik **derleme olarak** ayarını **C kodu olarak derle (/ TC)**.

## <a name="project-templates"></a>Proje şablonları

Visual Studio'daki proje şablonları, ürün sürümü ve yüklediğiniz iş yükleri bağlıdır. Masaüstü uygulama geliştirme ile C++ iş yükünü yüklediyseniz, Visual Studio'nun bu Visual C++ proje şablonları vardır.

### <a name="windows-desktop"></a>Windows Masaüstü

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[Windows konsol uygulaması](../../windows/creating-a-console-application.md)|Bir Windows konsol uygulaması oluşturmaya yönelik bir proje.|
|[Windows masaüstü uygulaması](../../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Windows Masaüstü (Win32) uygulaması oluşturmaya yönelik bir proje.|
|[Dinamik bağlantı kitaplığı](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|Bir dinamik bağlantı kitaplığı (DLL) oluşturmak için bir proje.|
|[Statik kitaplık](../../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Statik kitaplık (LIB) oluşturmak için bir proje.|
|Windows Masaüstü Sihirbazı|Ek seçenekler ile Windows Masaüstü uygulamaları ve kitaplıkları oluşturmak için bir sihirbaz.|

### <a name="general"></a>Genel

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|Boş Proje|Bir uygulama, kitaplık veya DLL'i oluşturmak için boş proje. Herhangi bir kod veya gerekli kaynakları eklemeniz gerekir.|
|[Derleme görevleri dosyası projesi](creating-a-makefile-project.md)|Visual Studio projede derleme görevleri dosyası Windows sarmalayan bir proje. (Derleme görevleri dosyası olarak açmak için-Visual Studio kullanımı [klasörünü Aç](../open-folder-projects-cpp.md).|
|Paylaşılan öğeler projesi|Kod veya kaynak dosyalar birden çok proje arasında paylaşmak için kullanılan bir proje. Bu proje türü, yürütülebilir bir dosya oluşturmaz.|

### <a name="atl"></a>ATL

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[ATL projesi](../../atl/reference/creating-an-atl-project.md)|Etkin Şablon Kütüphanesi kullanan bir proje.|

### <a name="test"></a>Test

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[Yerel birim testi projesi](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|Yerel C++ birim testleri içeren bir proje.|

### <a name="mfc"></a>MFC

Visual Studio yüklemenizin bileşenine MFC ve ATL desteği eklerseniz, bu proje şablonları için Visual Studio eklenir.

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[MFC uygulaması](../../mfc/reference/creating-an-mfc-application.md)|Microsoft Foundation Class (MFC) kitaplığı kullanan bir uygulama oluşturmaya yönelik bir proje.|
|[MFC ActiveX denetimi](../../mfc/reference/creating-an-mfc-activex-control.md)|MFC kitaplığını kullanan ActiveX denetimi oluşturmak için bir proje.|
|[MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)|MFC Kitaplığı'nı kullanan dinamik bağlantı kitaplığı oluşturma projesi.|

### <a name="windows-universal-apps"></a>Evrensel Windows uygulamaları

Visual Studio yüklemenizin C++ Evrensel Windows platformu araçları bileşeni eklerseniz, bu proje şablonları, Visual Studio'ya eklenir.

C++'ta Windows Evrensel uygulamaları genel bakış için bkz. [Evrensel Windows uygulamaları (C++)](../../windows/universal-windows-apps-cpp.md).

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|Boş Uygulama|Önceden tanımlanmış denetimleri veya düzeni olmayan tek sayfalık bir evrensel Windows Platformu (UWP) uygulama projesi.|
|DirectX 11 uygulaması|DirectX 11 kullanan bir evrensel Windows platformu uygulamasına yönelik bir proje.|
|DirectX 12 uygulaması|DirectX 12 kullanan bir evrensel Windows platformu uygulamasına yönelik bir proje.|
|DirectX 11 ve XAML uygulaması|DirectX 11 ve XAML kullanan bir evrensel Windows platformu uygulaması için bir proje.|
|Birim testi uygulaması|Evrensel Windows Platformu (UWP) uygulamaları için birim testi uygulaması oluşturmaya yönelik bir proje.|
|DLL|Evrensel Windows platformu uygulaması veya çalışma zamanı bileşeni tarafından kullanılabilen yerel dinamik bağlantı kitaplığı (DLL) projesi.|
|Statik kitaplık|Evrensel Windows platformu uygulaması veya çalışma zamanı bileşeni tarafından kullanılabilen yerel statik bağlantı kitaplığı (LIB) projesi.|
|Windows Çalışma Zamanı Bileşeni|Hangi programlama dilinde yazıldığına bakılmaksızın bir evrensel Windows platformu uygulaması tarafından kullanılabilen bir Windows çalışma zamanı bileşeni projesi.|
|Windows uygulaması paketleme projesi|Bir UWP paket oluşturan bir proje, dışarıdan yüklenen veya Microsoft Store aracılığıyla dağıtılmış bir masaüstü uygulaması sağlar.|

## <a name="todo-comments"></a>TODO yorumları

Birçok proje şablonu tarafından oluşturulan dosyalar, kendi kaynak kodunuz nerede sağlayabilirsiniz tanımlamanıza yardımcı olması için TODO açıklamaları içerir. Kodun nasıl ekleneceği hakkında daha fazla bilgi için bkz. [kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md) ve [kaynak dosyalarıyla çalışma](../../windows/working-with-resource-files.md).


