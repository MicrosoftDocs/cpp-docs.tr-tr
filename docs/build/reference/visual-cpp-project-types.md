---
title: Visual C++ Proje Türleri
ms.date: 08/13/2019
helpviewer_keywords:
- programs [C++], projects
- project templates [Visual Studio], C++
- TODO comments [C++]
- projects [C++], types
- templates [C++], projects
- applications [C++], projects
- C++ projects, types
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
ms.openlocfilehash: f234f9a05a871fe474b783a68f644cb4f2b1c2e7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498436"
---
# <a name="c-project-templates"></a>C++ proje şablonları

Visual Studio proje şablonları, oluşturmak istediğiniz proje türü için uygun olan kaynak kodu dosyalarını, derleyici seçeneklerini, menüleri, `#include` araç çubuklarını, simgeleri, başvuruları ve deyimleri oluşturur. Visual Studio çeşitli C++ proje şablonu türlerini içerir ve bunların birçoğu için sihirbazları sağlar, böylece projelerinizi oluşturduğunuz şekilde özelleştirebilirsiniz. Projeyi oluşturduktan hemen sonra, oluşturup uygulamayı çalıştırabilirsiniz; uygulamanızı geliştirirken zaman zaman oluşturmak iyi bir uygulamadır.

> [!NOTE]
> Proje şablonları kullanarak C++ C dili bir proje oluşturabilirsiniz. Oluşturulan projede,. cpp dosya adı uzantısına sahip dosyaları bulun ve. c olarak değiştirin. Ardından, proje için **Proje özellikleri** sayfasında (çözüm için değil), **yapılandırma özellikleri**, **C/C++**  öğesini genişletin ve **Gelişmiş**' i seçin. **Derleme olarak derle** ayarını **C kodu olarak derle (/TC)** olarak değiştirin.

## <a name="project-templates"></a>Proje şablonları

Visual Studio 'ya dahil edilen proje şablonları ürün sürümüne ve yüklediğiniz iş yüklerine bağlıdır. Masaüstü geliştirmeyi C++ iş yüküne yüklediyseniz, Visual Studio bu C++ proje şablonlarına sahiptir.

### <a name="windows-desktop"></a>Windows Masaüstü

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[Windows konsol uygulaması](../../windows/creating-a-console-application.md)|Windows konsol uygulaması oluşturmak için bir proje.|
|[Windows masaüstü uygulaması](../../windows/walkthrough-creating-windows-desktop-applications-cpp.md)|Windows Masaüstü (Win32) uygulaması oluşturmak için bir proje.|
|[Dinamik bağlantı kitaplığı](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)|Dinamik bağlantı kitaplığı (DLL) oluşturmak için bir proje.|
|[Statik kitaplık](../../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Statik kitaplık (LıB) oluşturmak için bir proje.|
|[Windows Masaüstü Sihirbazı](../../windows/windows-desktop-wizard.md)|Ek seçeneklerle Windows Masaüstü uygulamaları ve kitaplıkları oluşturmaya yönelik bir sihirbaz.|

### <a name="general"></a>Genel

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|Boş Proje|Uygulama, kitaplık veya DLL oluşturmak için boş bir proje. Gerekli herhangi bir kod veya kaynak eklemeniz gerekir.|
|[Makefile projesi](creating-a-makefile-project.md)|Bir Visual Studio projesinde Windows makefile 'ı sarmalayan bir proje. (Derleme görevleri dosyasını Visual Studio 'da olduğu gibi açmak için, [klasörü aç](../open-folder-projects-cpp.md)' ı kullanın.|
|Paylaşılan öğeler projesi|Birden çok proje arasında kod dosyalarını veya kaynak dosyalarını paylaşmak için kullanılan bir proje. Bu proje türü yürütülebilir bir dosya oluşturmuyor.|

### <a name="atl"></a>ATL

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[ATL projesi](../../atl/reference/creating-an-atl-project.md)|Etkin şablon kitaplığını kullanan bir proje.|

### <a name="test"></a>Test

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[Yerel birim testi projesi](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)|Yerel C++ birim testlerini içeren bir proje.|

### <a name="mfc"></a>MFC

MFC ve ATL desteği bileşenini Visual Studio yüklemenize eklerseniz, bu proje şablonları Visual Studio 'ya eklenir.

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|[MFC uygulaması](../../mfc/reference/creating-an-mfc-application.md)|Microsoft Foundation Class (MFC) kitaplığı kullanan bir uygulama oluşturmak için bir proje.|
|[MFC ActiveX denetimi](../../mfc/reference/creating-an-mfc-activex-control.md)|MFC kitaplığı kullanan ActiveX denetimi oluşturmak için bir proje.|
|[MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)|MFC kitaplığını kullanan bir dinamik bağlantı kitaplığı oluşturmak için bir proje.|

### <a name="windows-universal-apps"></a>Windows Evrensel uygulamaları

Visual Studio yüklemenize C++ Windows Universal platform araçları bileşeni eklerseniz, bu proje şablonları Visual Studio 'ya eklenir.

İçindeki C++Windows Evrensel uygulamalarına genel bakış için bkz. [Evrensel Windows uygulamaları (C++)](../../cppcx/universal-windows-apps-cpp.md).

|Proje şablonu|Açıklama|
|----------------------|-----------------------------|
|Boş Uygulama|Önceden tanımlanmış denetimleri veya düzeni olmayan tek sayfalı Evrensel Windows Platformu (UWP) uygulamasına yönelik bir proje.|
|DirectX 11 uygulaması|DirectX 11 kullanan Evrensel Windows Platformu uygulamasına yönelik bir proje.|
|DirectX 12 uygulaması|DirectX 12 kullanan Evrensel Windows Platformu uygulama için bir proje.|
|DirectX 11 ve XAML uygulaması|DirectX 11 ve XAML kullanan bir Evrensel Windows Platformu uygulaması için proje.|
|Birim test uygulaması|Evrensel Windows Platformu (UWP) uygulamaları için birim testi uygulaması oluşturmaya yönelik bir proje.|
|DLL|Bir Evrensel Windows Platformu uygulaması veya çalışma zamanı bileşeni tarafından kullanılabilen yerel dinamik bağlantı kitaplığı (DLL) projesi.|
|Statik kitaplık|Bir Evrensel Windows Platformu uygulaması veya çalışma zamanı bileşeni tarafından kullanılabilen yerel statik bağlantı kitaplığı (LıB) projesi.|
|Windows Çalışma Zamanı Bileşeni|Uygulamanın yazıldığı programlama dilinden bağımsız olarak, bir Evrensel Windows Platformu uygulaması tarafından kullanılabilen bir Windows Çalışma Zamanı bileşeni projesi.|
|Windows uygulaması paketleme projesi|Bir masaüstü uygulamasının Microsoft Store aracılığıyla dışarıdan yüklenmesini veya dağıtılmasını sağlayan UWP paketi oluşturan bir proje.|

## <a name="todo-comments"></a>TODO açıklamaları

Bir proje şablonu tarafından oluşturulan dosyaların birçoğu, kendi kaynak kodunuzu sağlayabileceğiniz yeri belirlemenize yardımcı olacak TODO açıklamalarını içerir. Kod ekleme hakkında daha fazla bilgi için bkz. [kod sihirbazları Ile Işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md) ve [kaynak dosyalarıyla çalışma](../../windows/working-with-resource-files.md).


