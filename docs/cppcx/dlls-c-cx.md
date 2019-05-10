---
title: DLLs (C++/CX)
ms.date: 02/06/2018
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
ms.openlocfilehash: 13e733f0be27fe532af6109bdd6fc53291265e66
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447244"
---
# <a name="dlls-ccx"></a>DLLs (C++/CX)

Visual Studio standart bir Win32 DLL ya da bir Windows çalışma zamanı bileşeni Evrensel Windows Platformu (UWP) uygulamaları tarafından tüketilebilecek DLL'i oluşturmak için kullanabilirsiniz. Visual Studio veya Microsoft bir sürümü kullanılarak oluşturulmuş olan standart bir DLL C++ Visual Studio 2012 bir UWP uygulamasında doğru yüklenmeyebilir ve uygulama doğrulama testi içinde Microsoft Store geçecek değil daha önceki bir derleyici.

## <a name="windows-runtime-component-dlls"></a>Windows çalışma zamanı bileşeni DLL'leri

Hemen hemen tüm durumlarda oluşturmak istediğinizde bir DLL için bir UWP uygulamasında kullanmak, bu ada sahip proje şablonunu kullanarak bir Windows çalışma zamanı bileşeni olarak oluşturun. Genel veya özel Windows çalışma zamanı türlerine sahip dll dosyaları için bir Windows çalışma zamanı bileşeni projesi oluşturabilirsiniz. Bir Windows çalışma zamanı bileşeni, herhangi bir Windows çalışma zamanı ile uyumlu dilde yazılmış uygulamalardan erişilebilir. Varsayılan olarak, derleyici ayarları bir Windows çalışma zamanı bileşeni proje kullanım **/ZW** geçin. .Winmd dosyası, kök ad alanı olan aynı ada sahip olmalıdır. Örneğin, yalnızca A.winmd veya A.B.winmd veya A.B.C.winmd adlı bir meta veri dosyasında tanımlanan A.B.C.MyClass adlı bir sınıf oluşturulabilir. DLL adını .winmd dosyası adı ile eşleşmesi için gerekli değildir.

Daha fazla bilgi için [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>Bir üçüncü taraf Windows çalışma zamanı bileşeni projenize ikili k odkazu

1. DLL kullanın ve ardından Proje için kısayol menüsünü açın **özellikleri**. Üzerinde **ortak özellikler** sayfasında **Yeni Başvuru Ekle** düğmesi.

1. Bir Windows çalışma zamanı bileşeni bir DLL dosyası ve meta veriler içeren bir .winmd dosyası oluşur. Genellikle, bu dosyalar aynı klasörde bulunur. Sol bölmesinde **Başvuru Ekle** iletişim kutusunda **Gözat** düğmesine tıklayın ve ardından DLL ve kendi .winmd dosyasının konumuna gidin. Daha fazla bilgi için [uzantı SDK'ları](/visualstudio/extensibility/creating-a-software-development-kit#ExtensionSDKs).

## <a name="standard-dlls"></a>Standart DLL'leri

Kullanma veya ortak Windows çalışma zamanı türleri üretmek ve JavaScript'ten bir UWP uygulaması kullanma C++ kodu için standart bir DLL oluşturabilirsiniz. Yalnızca Visual Studio'nun bu sürümünde derleme ancak bir Windows çalışma zamanı bileşeni projesi için kod dönüştürmemenizi için mevcut bir DLL geçirmek istediğinizde dinamik bağlantı kitaplığı (DLL) projesi türünü kullanın. Aşağıdaki adımlarda kullandığınız zaman uygulamanızın .appx paketinde yürütülebilir yanı sıra DLL dağıtılır.

### <a name="to-create-a-standard-dll-in-visual-studio"></a>Visual Studio'da standart bir DLL oluşturma

1. Menü çubuğunda, **dosya**, **yeni**, **proje**ve ardından **dinamik bağlantı kitaplığı (DLL)** şablonu.

1. Proje için bir ad girin ve ardından **Tamam** düğmesi.

1. Kodu ekleyin. Kullandığınızdan emin olun `__declspec(dllexport)` dışarı aktarmak için istediğinize işlevler için — örneğin, `__declspec(dllexport) Add(int I, in j);`

1. Ekleme `#include winapifamily.h` UWP uygulamaları için Windows SDK, üstbilgi dosyasını dahil edin ve makro ayarlamak için `WINAPI_FAMILY=WINAPI_PARTITION_APP`.

### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>Aynı çözümdeki standart bir DLL projesi başvurmak için

1. DLL kullanın ve ardından Proje için kısayol menüsünü açın **özellikleri**. Üzerinde **ortak özellikler** sayfasında **Yeni Başvuru Ekle** düğmesi.

1. Sol bölmede seçin **çözüm**ve ardından sağ bölmede ilgili onay kutusunu seçin.

1. Kaynak kodu dosyalarında ekleme bir `#include` deyimi için gerektiği şekilde DLL üst bilgi dosyası.

### <a name="to-reference-a-standard-dll-binary"></a>Standart bir DLL ikili k odkazu

1. DLL dosyasının, .lib dosyası ve üstbilgi dosyasını kopyalayın ve bunları bilinen bir konuma yapıştırın — Örneğin, geçerli proje klasörünüzdeki.

1. DLL kullanın ve ardından Proje için kısayol menüsünü açın **özellikleri**. Üzerinde **yapılandırma özellikleri**, **bağlayıcı**, **giriş** sayfasında, .lib dosyasına bağımlılık olarak ekleyin.

1. Kaynak kodu dosyalarında ekleme bir `#include` deyimi için gerektiği şekilde DLL üst bilgi dosyası.

### <a name="to-migrate-an-existing-win32-dll-for-uwp-app-compatibility"></a>UWP uygulama uyumluluğu için mevcut bir Win32 DLL geçirmek için

1. DLL (Evrensel Windows) türü bir proje oluşturun ve mevcut kaynak kod ekleyin.

1. Ekleme `#include winapifamily.h` UWP uygulamaları için Windows SDK, üstbilgi dosyasını dahil edin ve makro ayarlamak için `WINAPI_FAMILY=WINAPI_PARTITION_APP`.

1. Kaynak kodu dosyalarında ekleme bir `#include` deyimi için gerektiği şekilde DLL üst bilgi dosyası.
