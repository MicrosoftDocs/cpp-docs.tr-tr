---
description: "Daha fazla bilgi edinin: DLL 'Ler (C++/CX)"
title: DLL’ler (C++/CX)
ms.date: 02/06/2018
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
ms.openlocfilehash: 6290da444b463744315a55304a68e8ab165fc162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341990"
---
# <a name="dlls-ccx"></a>DLL’ler (C++/CX)

Visual Studio 'Yu, standart bir Win32 DLL veya Evrensel Windows Platformu (UWP) uygulamaları tarafından tüketilen bir Windows Çalışma Zamanı Component DLL oluşturmak için kullanabilirsiniz. Visual Studio 'nun bir sürümü kullanılarak oluşturulmuş standart bir DLL veya Visual Studio 2012 ' den önceki Microsoft C++ derleyicisi, UWP uygulamasında düzgün yüklenmeyebilir ve Microsoft Store uygulama doğrulama testini geçemeyebilir.

## <a name="windows-runtime-component-dlls"></a>Windows Çalışma Zamanı bileşen DLL 'Leri

Neredeyse tüm durumlarda, UWP uygulamasında kullanmak üzere bir DLL oluşturmak istediğinizde, bu adın proje şablonunu kullanarak bir Windows Çalışma Zamanı bileşeni olarak oluşturun. Ortak veya özel Windows Çalışma Zamanı türlerine sahip dll 'Ler için Windows Çalışma Zamanı bileşen projesi oluşturabilirsiniz. Windows Çalışma Zamanı bileşene, Windows Çalışma Zamanı uyumlu herhangi bir dilde yazılan uygulamalardan erişilebilir. Varsayılan olarak, bir Windows Çalışma Zamanı bileşen projesi için derleyici ayarları **/ZW** anahtarını kullanır. Bir. winmd dosyası, kök ad alanıyla aynı ada sahip olmalıdır. Örneğin, A. B. C. MyClass adlı bir sınıf, yalnızca bir. winmd veya A. B. winmd veya A. B. C. winmd adında bir meta veri dosyasında tanımlanmışsa oluşturulabilir. DLL 'nin adı. winmd dosya adıyla eşleşmek için gerekli değildir.

Daha fazla bilgi için bkz. [C++ ' de Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>Projenizdeki bir üçüncü taraf Windows Çalışma Zamanı bileşen ikilisini başvurmak için

1. DLL 'yi kullanacak proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin. **Ortak özellikler** sayfasında, **Yeni Başvuru Ekle** düğmesini seçin.

1. Bir Windows Çalışma Zamanı bileşeni, meta verileri içeren bir DLL dosyasından ve. winmd dosyasından oluşur. Genellikle, bu dosyalar aynı klasörde bulunur. **Başvuru Ekle** iletişim kutusunun sol **bölmesinde, e-bul düğmesini SEÇIN** ve ardından dll ve. winmd dosyasının konumuna gidin. Daha fazla bilgi için bkz. [Uzantı SDK 'ları](/visualstudio/extensibility/creating-a-software-development-kit#extension-sdks).

## <a name="standard-dlls"></a>Standart DLL 'Ler

Ortak Windows Çalışma Zamanı türlerini tüketmeyen veya üretmeyen C++ kodu için standart bir DLL oluşturabilir ve bunu UWP uygulamasından kullanabilirsiniz. Yalnızca var olan bir DLL 'yi Visual Studio 'nun bu sürümünde derlemek üzere geçirmek istediğinizde, ancak kodu bir Windows Çalışma Zamanı bileşen projesine dönüştürmeyeceğiniz zaman Dynamic-Link kitaplığı (DLL) proje türünü kullanın. Aşağıdaki adımları kullandığınızda, DLL. appx paketinde uygulamanızın yürütülebilir dosyası ile birlikte dağıtılır.

### <a name="to-create-a-standard-dll-in-visual-studio"></a>Visual Studio 'da Standart DLL oluşturmak için

1. Menü çubuğunda **Dosya**, **Yeni**, **Proje**' yi seçin ve ardından **dinamik bağlantı kitaplığı (dll)** şablonunu seçin.

1. Proje için bir ad girin ve **Tamam** düğmesini seçin.

1. Kodu ekleyin. `__declspec(dllexport)`Dışarı aktarmayı düşündüğünüz işlevler için kullandığınızdan emin olun — Örneğin,`__declspec(dllexport) Add(int I, in j);`

1. `#include winapifamily.h`UWP uygulamaları için Windows SDK üst bilgi dosyasını dahil etmek ve makroyu ayarlamak için ekleyin `WINAPI_FAMILY=WINAPI_PARTITION_APP` .

### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>Aynı çözümden standart bir DLL projesine başvurmak için

1. DLL 'yi kullanacak proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin. **Ortak özellikler** sayfasında, **Yeni Başvuru Ekle** düğmesini seçin.

1. Sol bölmede **çözüm**' ü seçin ve sağ bölmedeki ilgili onay kutusunu seçin.

1. Kaynak kodu dosyalarınızda, `#include` gereken şekılde dll üstbilgi dosyası için bir ifade ekleyin.

### <a name="to-reference-a-standard-dll-binary"></a>Standart bir DLL ikiliye başvurmak için

1. DLL dosyasını,. lib dosyasını ve üst bilgi dosyasını kopyalayın ve bu dosyaları bilinen bir konuma (örneğin, geçerli proje klasörünüzde) yapıştırın.

1. DLL 'yi kullanacak proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin. **Yapılandırma özellikleri**, **bağlayıcı**, **giriş** sayfasında,. lib dosyasını bir bağımlılık olarak ekleyin.

1. Kaynak kodu dosyalarınızda, `#include` gereken şekılde dll üstbilgi dosyası için bir ifade ekleyin.

### <a name="to-migrate-an-existing-win32-dll-for-uwp-app-compatibility"></a>UWP uygulama uyumluluğu için mevcut bir Win32 DLL 'yi geçirmek için

1. DLL (Evrensel Windows) türünde bir proje oluşturun ve var olan kaynak kodunuzu buna ekleyin.

1. `#include winapifamily.h`UWP uygulamaları için Windows SDK üst bilgi dosyasını dahil etmek ve makroyu ayarlamak için ekleyin `WINAPI_FAMILY=WINAPI_PARTITION_APP` .

1. Kaynak kodu dosyalarınızda, `#include` gereken şekılde dll üstbilgi dosyası için bir ifade ekleyin.
