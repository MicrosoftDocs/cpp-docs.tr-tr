---
title: DLL'ler (C + +/ CX) | Microsoft Docs
ms.custom: 
ms.date: 02/06/2018
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f483494d981a03816a8b2717b9ad5098a8a714c9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="dlls-ccx"></a>DLL'ler (C + +/ CX)

Standart Win32 DLL ya da Windows çalışma zamanı bileşeni Evrensel Windows Platformu (UWP) uygulamaları tarafından kullanılabilecek DLL oluşturmak için Visual Studio'yu kullanabilirsiniz. Visual Studio veya Visual Studio 2012 UWP uygulamasında doğru yüklenmeyebilir ve uygulaması doğrulama testi Microsoft Store iletebilir değil daha önceki Visual C++ Derleyici sürümü kullanılarak oluşturulmuş bir standart DLL.

## <a name="windows-runtime-component-dlls"></a>Windows çalışma zamanı bileşeni DLL'leri

Neredeyse tüm durumlarda oluşturmak istediğinizde bir DLL için bir UWP uygulamasında kullanma, o adı proje şablonunu kullanarak bir Windows çalışma zamanı bileşeni olarak oluşturun. Genel veya özel Windows çalışma zamanı türlerine sahip DLL'ler için bir Windows çalışma zamanı bileşeni proje oluşturabilirsiniz. Windows çalışma zamanı bileşeni herhangi bir Windows çalışma zamanı uyumlu dilde yazılan uygulamalardan erişilebilir. Varsayılan olarak, bir Windows çalışma zamanı bileşeni için derleyici ayarlarını proje kullanım **/ZW** geçin. Bir .winmd dosyası kök ad alanı var. aynı ada sahip olmalıdır. Örneğin, yalnızca A.winmd veya A.B.winmd veya A.B.C.winmd adlı bir meta veri dosyasında tanımlanırsa A.B.C.MyClass adlı bir sınıf oluşturulabilir. DLL adını .winmd dosya adı ile eşleşmesi için gerekli değildir.

Daha fazla bilgi için bkz: [C++'da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>Bir üçüncü taraf Windows çalışma zamanı bileşeni projenize ikili başvurmak için

1. DLL kullanın ve ardından Proje için kısayol menüsünü açın **özellikleri**. Üzerinde **ortak özellikleri** sayfasında, **Yeni Başvuru Ekle** düğmesi.

1. Windows çalışma zamanı bileşeni DLL dosyasının ve meta verileri içeren bir .winmd dosyası oluşur. Genellikle, bu dosyalar aynı klasörde bulunur. Sol bölmesinde **Başvuru Ekle** iletişim kutusunda, seçin **Gözat** düğmesine tıklayın ve ardından DLL ve .winmd dosyası konumuna gidin. Daha fazla bilgi için bkz: [uzantısı SDK'ları](/visualstudio/extensibility/creating-a-software-development-kit#ExtensionSDKs).

## <a name="standard-dlls"></a>Standart DLL'leri

Standart bir DLL değil kullanabilir veya genel Windows çalışma zamanı tür üreten ve JavaScript'ten bir UWP uygulaması kullanma C++ kodu için oluşturabilirsiniz. Yalnızca Visual Studio'nun bu sürümünde derleme ancak kod Windows çalışma zamanı bileşeni projeye dönüştürmemenizi için var olan bir DLL geçirmek istediğiniz dinamik bağlantı kitaplığı (DLL) proje türü kullanın. Aşağıdaki adımları kullandığınızda, DLL uygulamanızı .appx paketinde yürütülebilir yanında dağıtılır.

### <a name="to-create-a-standard-dll-in-visual-studio"></a>Visual Studio'da standart DLL oluşturmak için

1. Menü çubuğunda seçin **dosya**, **yeni**, **proje**ve ardından **dinamik bağlantı kitaplığı (DLL)** şablonu.

1. Proje için bir ad girin ve ardından **Tamam** düğmesi.

1. Kodu ekleyin. Kullandığınızdan emin olun `__declspec(dllexport)` dışarı aktarmak istediğiniz işlevler için — örneğin, `__declspec(dllexport) Add(int I, in j);`

1. Ekleme `#include winapifamily.h` UWP uygulamalar için Windows SDK bu üst bilgi dosyasını dahil ve makrosu ayarlamak için `WINAPI_FAMILY=WINAPI_PARTITION_APP`.

### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>Aynı çözümden başvuru standart DLL projesi

1. DLL kullanın ve ardından Proje için kısayol menüsünü açın **özellikleri**. Üzerinde **ortak özellikleri** sayfasında, **Yeni Başvuru Ekle** düğmesi.

1. Sol bölmede seçin **çözüm**ve ardından sağ bölmede uygun onay kutusunu seçin.

1. Kaynak kodu dosyalarınızda eklemek bir `#include` gerektiğinde DLL üstbilgi dosyası bildirimi.

### <a name="to-reference-a-standard-dll-binary"></a>Standart bir DLL ikili başvurmak için

1. DLL dosyası, .lib dosya ve üstbilgi dosyası kopyalayın ve bilinen bir konuma Yapıştır — Örneğin, geçerli proje klasörünüzdeki.

1. DLL kullanın ve ardından Proje için kısayol menüsünü açın **özellikleri**. Üzerinde **yapılandırma özellikleri**, **bağlayıcı**, **giriş** sayfasında, bir bağımlılık olarak .lib dosyası ekleyin.

1. Kaynak kodu dosyalarınızda eklemek bir `#include` gerektiğinde DLL üstbilgi dosyası bildirimi.

### <a name="to-migrate-an-existing-win32-dll-for-uwp-app-compatibility"></a>UWP uygulama uyumluluğu için varolan bir Win32 DLL geçirmek için

1. DLL (Evrensel Windows) türündeki bir proje oluşturun ve mevcut kaynak kodu ekleyin.

1. Ekleme `#include winapifamily.h` UWP uygulamalar için Windows SDK bu üst bilgi dosyasını dahil ve makrosu ayarlamak için `WINAPI_FAMILY=WINAPI_PARTITION_APP`.

1. Kaynak kodu dosyalarınızda eklemek bir `#include` gerektiğinde DLL üstbilgi dosyası bildirimi.
