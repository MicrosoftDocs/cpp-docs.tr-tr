---
title: Kitaplıklar ve C++ projelerinde bileşenleri kullanma
ms.date: 12/10/2018
f1_keywords:
- VC.Project.References
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
ms.openlocfilehash: dff057977e6b6ff0c36d3a888bc4d5c3aa778576
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038773"
---
# <a name="consuming-libraries-and-components"></a>Kitaplıklar ve bileşenleri kullanma

Genellikle, arama işlevleri veya ikili dosyaları gibi statik kitaplık (.lib dosyaları), verilere erişmek bir C++ projesini gereken DLL, Windows çalışma zamanı bileşeni, COM bileşeni ya da .NET bütünleştirilmiş kodu. Bu durumlarda, oluşturma zamanında bu ikili bulabilirsiniz, böylece proje yapılandırmanız gerekir. İkili tür projenizin türüne belirli adımları bağlıdır ve projeniz gibi aynı çözüm içindeki ikili olup üretiliyor. 

## <a name="consuming-libraries-downloaded-via-vcpkg"></a>Vcpkg indirilen kitaplıkları kullanma

Kullanarak yüklediğiniz bir kitaplık kullanmak üzere **vcpkg** Paket Yöneticisi, aşağıdaki yönergeleri yok sayabilirsiniz. Bkz: [vcpkg: Windows, Linux ve MacOS için C++ Paket Yöneticisi](vcpkg.md#integrate-with-visual-studio-windows) daha fazla bilgi için.

## <a name="consuming-static-libraries"></a>Statik kitaplıklar kullanma

Aynı çözümdeki statik kitaplığı projenize oluşturuluyorsa:

1. #<a name="include-the-header-files-for-the-static-library-using-quotation-marks-in-a-typical-solution-the-path-will-start-with-library-project-name-intellisense-will-help-you-find-it"></a>tırnak işareti kullanarak statik kitaplık için üst bilgi dosyaları içerir. Tipik bir çözümde yolu ile başlar `../<library project name>`. IntelliSense bulmanıza yardımcı olur.
2. Statik kitaplık projesine bir başvuru ekleyin. Sağ **başvuruları** uygulama proje düğümü altında **Çözüm Gezgini** ve **Başvuru Ekle**. 

Statik kitaplık çözümün bir parçası değilse:

1. ' Nde uygulama proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**. 
2. İçinde **VC ++ dizinleri** özellik sayfasında, burada .lib dosyanın bulunduğu dizini yolu eklemek **kitaplık yollarını** ve kitaplığı üstbilgi dosyasında yolu eklemek **ekleme dizinleri** .  
3. İçinde **bağlayıcı > giriş** özellik sayfasında, eklemek için .lib dosyası adını **ek bağımlılıklar**.

## <a name="dynamic-link-libraries"></a>Dinamik bağlantı kitaplıkları

DLL, uygulamayla aynı çözümün parçası olarak oluşturuluyorsa, statik kitaplık olduğu gibi aynı adımları izleyin.

DLL uygulama çözümün bir parçası değilse, DLL dosyasına dışarı aktarılan işlevleri ve sınıfları için prototipleri ile üst ve gerekli bağlantı bilgileri sağlayan bir .lib dosyası gerekir.

1. DLL DLL'leri için proje çıktı klasörüne veya standart Windows arama yolu başka bir klasöre kopyalayın. Bkz: [dinamik bağlantı kitaplığı arama sırası](/windows/desktop/dlls/dynamic-link-library-search-order).
2. Statik kitaplıklar, üst bilgiler ve .lib dosyası yolları sağlamak için 1-3. adımları izleyin.

## <a name="com-objects"></a>COM nesneleri

Yerel C++ uygulamanızı bir COM nesnesi kullanmasını gerektiren durumlar ve söz konusu nesne ise *kayıtlı*, yapmanız gereken tek şey sonra CoCreateInstance çağırın ve nesneyi CLSID geçirin. Sistem, Windows kayıt defterinde bulun ve yükleyin. C + +/ CLI projesinin bir COM nesnesi olarak kullanabilir, aynı şekilde ya da ondan bir başvuru eklemeyi **başvuruları Ekle > COM** listesi ve aracılığıyla hangi kendi [çalışma zamanı çağrılabilir sarmalayıcı](/dotnet/framework/interop/runtime-callable-wrapper). 

## <a name="net-assemblies-and-windows-runtime-components"></a>.NET derlemelerini ve Windows çalışma zamanı bileşenleri

UWP veya C + +/ CLI projeleri .NET derlemeleri veya Windows çalışma zamanı bileşenleri ekleyerek kullanan bir *başvuru* derleme veya bileşen için. Altında **başvuruları** düğüm UWP veya C + +/ CLI projesinin, sık kullanılan bileşenleri başvurular bakın. Sağ **başvuruları** düğümünde **Çözüm Gezgini** ortaya çıkarmak için **başvuru Yöneticisi** ve göz atma sisteme bilinen ek bileşenler. Tıklayın **Gözat** düğmesini herhangi bir özel bileşene bulunduğu klasöre gidin. .NET derlemelerini ve Windows çalışma zamanı bileşenleri yerleşik tür bilgilerini içerdiğinden, yöntemleri ve sınıfları sağ tıklayıp seçerek görüntüleyebileceğiniz **Nesne Tarayıcısı görünümünde**. 

## <a name="reference-properties"></a>Başvuru özellikleri

Her tür başvurusu özellikleri vardır. Çözüm Gezgini'nde reference'ı seçip tuşuna basarak özelliklerini görüntüleyebilirsiniz **Alt + Enter**, veya başka sağ ve seçme **özellikleri**. Bazı özellikler salt okunurdur ve bazı değiştirilebilir. Ancak, genellikle bu özellikleri el ile değiştirmeniz gerekmez.

### <a name="activex-reference-properties"></a>ActiveX başvuru özellikleri

ActiveX başvurusu özellikleri yalnızca COM bileşenleri başvurular için kullanılabilir. Bu özellikler yalnızca bir COM bileşeni seçildiğinde görüntülenen **başvuruları** bölmesi. Özellikleri değiştirilemez.

- **Denetim tam yolu**

   Başvurulan denetimin dizin yolunu görüntüler.

- **Denetim GUID'i**

   ActiveX denetimi için GUID görüntüler.

- **Denetim sürümü**

   Başvurulan ActiveX denetiminin sürümünü görüntüler.

- **Tür kitaplığı adı**

   Başvurulan tür kitaplığının adı görüntüler.

- **Sarmalayıcı aracı**

   Başvurulan COM kitaplığından ya da ActiveX denetiminden birlikte çalışma derlemesi oluşturmak için kullanılan araç görüntüler.

### <a name="assembly-reference-properties-ccli"></a>Derleme başvurusu özellikleri (C + +/ CLI)

Derleme başvurusu özellikleri yüklenebilir yalnızca .NET Framework derlemelerine C + +/ CLI projeleri. .NET Framework derlemesi yalnızca seçildiğinde, bu özellikleri görüntülenir **başvuruları** bölmesi. Özellikleri değiştirilemez.

- **Göreli yolu**

   Proje dizininden başvurulan derlemeye göreli yolunu görüntüler.

### <a name="build-properties"></a>Derleme özellikleri

Aşağıdaki özellikler, çeşitli türlerdeki başvurular üzerinde kullanılabilir. Derleme başvuruları ile nasıl belirtmenize olanak tanırlar.

- **Yerele Kopyala**

   Başvurulan derlemenin bilgisayarın bir yapı sırasında hedef konuma otomatik olarak kopyalanıp kopyalanmayacağını belirtir.

- **Yerel uydu derlemelerini kopyala (C + +/ CLI)**

   Başvurulan derlemenin uydu derlemelerinin bilgisayarın bir yapı sırasında hedef konuma otomatik olarak kopyalanıp kopyalanmayacağını belirtir. Yalnızca **Yereli Kopyala** olduğu **true**.

- **Başvuru bütünleştirilmiş kodu çıkışı**

   Bu derlemenin yapı işleminde kullanıldığını belirtir. Varsa **true**, derleme yapı sırasında derleyici komut satırında kullanılır.

### <a name="project-to-project-reference-properties"></a>Projeden projeye başvuru özellikleri

Aşağıdaki özellikleri tanımlayan bir *projeden projeye başvuru* seçili projeden **başvuruları** aynı çözümdeki başka bir projeye bölmesi. Daha fazla bilgi için [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

- **Bağlantı kitaplığı bağımlılıkları**

   Bu özellik olduğunda **True**, proje sistemi bağımsız proje tarafından üretilen .lib dosyaları bağımlı projesine bağlar. Genellikle, belirteceği **True**.

- **Proje tanımlayıcısı**

   Bağımsız projenin benzersiz olarak tanımlar. Özelliği bir iç sistem değiştirilemez GUID değeridir.

- **Kitaplık bağımlılığı girişlerini kullan**

   Bu özellik olduğunda **False**, proje sistemi bağımlı projeye bağımsız proje tarafından üretilen kitaplığı .obj dosyaları bağlayacaksınız değil. Sonuç olarak, bu değer artımlı bağlamayı devre dışı bırakır. Genellikle, belirteceği **False** çünkü uygulama oluşturma çok sayıda bağımsız proje ise bir uzun zaman alabilir.

### <a name="read-only-reference-properties-com--net"></a>Salt okunur başvuru özellikleri (COM ve .NET)

Aşağıdaki özellikleri, COM ve .NET derleme başvurularını bulunur ve değiştirilemez.

- **Derleme adı**

   Başvurulan derlemenin derleme adını görüntüler.

- **Kültür**

   Seçilen başvurunun kültürü görüntüler.

- **Açıklama**

   Seçilen başvurunun açıklaması görüntüler.

- **Tam yolu**

   Başvurulan derlemenin dizin yolunu görüntüler.

- **Kimlik**

   .NET Frameworkassemblies için tam yolunu görüntüler. COM bileşenleri için GUID görüntüler.

- **Etiketle**

   Başvurunun etiketi görüntüler.

- **Ad**

   Başvuru adını görüntüler.

- **Ortak anahtar belirteci**

   Başvurulan derlemeyi tanımlamak için kullanılan ortak anahtar belirtecini görüntüler.

- **Tanımlayıcı ad**

   `true` başvurulan derlemenin tanımlayıcı ad varsa. Bir tanımlayıcı adlı derleme sürümlüdür.

- **Sürüm**

   Başvurulan derlemenin sürümünü gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ projesi özellik Sayfa başvurusu](reference/property-pages-visual-cpp.md)<br>
[C++ derleyicisi ayarlayın ve derleme Visual Studio özellikleri](working-with-project-properties.md)