---
description: 'Hakkında daha fazla bilgi edinin: kitaplıkları ve bileşenleri kullanma'
title: C++ projelerinde kitaplıkları ve bileşenleri kullanma
ms.date: 12/18/2020
f1_keywords:
- VC.Project.References
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
ms.openlocfilehash: c8e7cb41fad6a974ac677228d884a31e4fa92ce1
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97682459"
---
# <a name="consuming-libraries-and-components"></a>Kitaplıkları ve bileşenleri kullanma

C++ projelerinin genellikle statik kitaplık (LıB dosyaları), DLL, Windows Çalışma Zamanı bileşeni, COM bileşeni veya .NET derlemesi gibi bir ikili dosyadaki işlevleri çağırması veya verilere erişmesi gerekir. Bu gibi durumlarda, projenin derleme zamanında bu ikiliyi bulabileceği şekilde yapılandırmasını sağlayabilirsiniz. Belirli adımlar projenizin türüne, ikili türüne ve ikili dosyanın projeniz ile aynı çözümde oluşturulup oluşturulmadığına bağlıdır.

## <a name="consuming-libraries-downloaded-via-vcpkg"></a>Vcpkg aracılığıyla indirilen kitaplıkları kullanma

**Vcpkg** paket yöneticisini kullanarak indirdiğiniz bir kitaplığı kullanmak için aşağıdaki yönergeleri yoksayabilirsiniz. Daha fazla bilgi için bkz. [vcpkg: Windows, Linux ve macOS Için C++ Paket Yöneticisi](vcpkg.md) .

## <a name="consuming-static-libraries"></a>Statik kitaplıkları kullanma

Statik kitaplık projeniz aynı çözümde inşa edildiğinde:

1. #<a name="include-the-header-files-for-the-static-library-using-quotation-marks-in-a-typical-solution-the-path-starts-with-library-project-name-intellisense-will-help-you-find-it"></a>tırnak işaretleri kullanarak statik kitaplık için üst bilgi dosyalarını ekleyin. Tipik bir çözümde yol ile başlar `../<library project name>` . IntelliSense onu bulmanıza yardımcı olur.
2. Statik kitaplık projesine bir başvuru ekleyin. **Çözüm Gezgini** içindeki uygulama projesi düğümünün altında **Başvurular** ' a sağ tıklayın ve **Başvuru Ekle**' yi seçin.

Statik kitaplık çözümün bir parçası değilse:

1. **Çözüm Gezgini** ' de uygulama projesi düğümüne sağ tıklayın ve ardından **Özellikler**' i seçin.
2. **VC + + dizinleri** Özellik sayfasında, **KITAPLıĞı yollarındaki** LIB dosyasını içeren dizine yolu ekleyin. Ardından, **Dizin** eklemek için kitaplık üstbilgi dosyalarının yolunu ekleyin.  
3. **Bağlayıcı > girişi** özelliği SAYFASıNDA, LIB dosyasının adını **ek bağımlılıklara** ekleyin.

## <a name="dynamic-link-libraries"></a>Dinamik bağlantı kitaplıkları

DLL, uygulamayla aynı çözümün parçası olarak derlenirse, bir statik kitaplık için aynı adımları izleyin.

DLL, uygulama çözümünün bir parçası değilse, şunlar gerekir: DLL dosyası, içe aktarılmış işlevler ve sınıflar için Prototiplerde bulunan üst bilgiler ve gerekli bağlantı bilgilerini sağlayan bir LıB dosyası.

1. DLL 'yi projenizin çıkış klasörüne veya dll 'Ler için standart Windows arama yolundaki başka bir klasöre kopyalayın. Bkz. [dinamik bağlantı kitaplığı arama sırası](/windows/win32/dlls/dynamic-link-library-search-order).
2. Üst bilgiler ve LıB dosyasına yolları sağlamak için statik kitaplıkların 1-3 adımlarını izleyin.

## <a name="com-objects"></a>COM nesneleri

Yerel C++ uygulamanızın bir COM nesnesini kullanması gerekiyorsa ve bu nesne *kayıtlıysa*, tüm yapmanız gereken, CoCreateInstance çağrısı yapın ve nesnenin CLSID 'sini geçirin. Sistem bunu Windows kayıt defterinde bulur ve yükler. C++/CLı projesi bir COM nesnesini aynı şekilde kullanabilir. Ya da, **başvuruları ekle > com** listesinden buna bir başvuru ekleyerek ve bu dosyayı [çalışma zamanı çağrılabilir sarmalayıcı](/dotnet/framework/interop/runtime-callable-wrapper)aracılığıyla kullanarak kullanabilir.

## <a name="net-assemblies-and-windows-runtime-components"></a>.NET derlemeleri ve Windows Çalışma Zamanı bileşenleri

UWP veya C++/CLı projelerinde, derleme veya bileşene bir *başvuru* ekleyerek .NET derlemelerini veya Windows çalışma zamanı bileşenlerini kullanırsınız. UWP veya C++/CLı projesindeki **Başvurular** düğümü altında, yaygın olarak kullanılan bileşenlere başvurular görürsünüz. **Başvuru yöneticisini** açmak ve sistemde bulunan bileşenlere göz atarak **Çözüm Gezgini** içindeki **Başvurular** düğümüne sağ tıklayın. Özel bir bileşen içeren herhangi bir klasöre gitmek için, **tarayıcı** düğmesini seçin. .NET derlemeleri ve Windows Çalışma Zamanı bileşenleri yerleşik tür bilgilerini içerdiğinden, kendi yöntemlerini ve sınıflarını sağ tıklayıp, **nesne tarayıcısı görüntüle '** yi seçerek görüntüleyebilirsiniz.

## <a name="reference-properties"></a>Başvuru özellikleri

Her bir başvuru türü için özellikler vardır. Çözüm Gezgini içindeki başvuruyu seçerek ve **Alt + Enter** tuşlarına basarak veya sağ tıklayıp **Özellikler**' i seçerek özellikleri görüntüleyebilirsiniz. Bazı özellikler salt okunurdur ve bazıları değiştirilebilir. Ancak, bu özellikleri genellikle el ile değiştirmeniz gerekmez.

### <a name="activex-reference-properties"></a>ActiveX başvuru özellikleri

ActiveX başvuru özellikleri yalnızca COM bileşenlerine yönelik başvurular için kullanılabilir. Bu özellikler yalnızca **Başvurular** BÖLMESINDE bir com bileşeni seçtiğinizde gösterilir. Özellikler değiştirilebilir değildir.

- **Denetim tam yolu**

   Başvurulan denetimin dizin yolunu görüntüler.

- **Denetim GUID 'ı**

   ActiveX denetimi için GUID görüntüler.

- **Denetim sürümü**

   Başvurulan ActiveX denetiminin sürümünü görüntüler.

- **Tür kitaplığı adı**

   Başvurulan tür kitaplığının adını görüntüler.

- **Sarmalayıcı aracı**

   Başvurulan COM kitaplığından ya da ActiveX denetiminden birlikte çalışma derlemesini derlemek için kullanılan aracı görüntüler.

### <a name="assembly-reference-properties-ccli"></a>Bütünleştirilmiş kod başvuru özellikleri (C++/CLı)

Bütünleştirilmiş kod başvuru özellikleri yalnızca C++/CLı projelerinde .NET Framework derlemelerine yapılan başvurular için kullanılabilir. Bu özellikler yalnızca **Başvurular** bölmesinde bir .NET Framework derlemesi seçtiğinizde gösterilir. Özellikler değiştirilebilir değildir.

- **Göreli yol**

   Proje dizininden başvurulan derlemeye göreli yolu görüntüler.

### <a name="build-properties"></a>Derleme özellikleri

Aşağıdaki özellikler çeşitli türlerde başvurularda kullanılabilir. Bunlarla nasıl derleme yapılacağını belirtmenize olanak tanır.

- **Yereli Kopyala**

   Başvurulan derlemenin derleme sırasında hedef konuma otomatik olarak kopyalanıp kopyalanmayacağını belirtir.

- **Yerel uydu derlemelerini kopyalama (C++/CLı)**

   Başvurulan derlemenin uydu derlemelerinin derleme sırasında hedef konuma otomatik olarak kopyalanıp kopyalanmayacağını belirtir. Yalnızca yereli **Kopyala** ise kullanılır **`true`** .

- **Başvuru bütünleştirilmiş kodu çıkışı**

   Bu derlemenin yapı işleminde kullanıldığını belirtir. İse **`true`** , derleme sırasında derleyici komut satırında derleme kullanılır.

### <a name="project-to-project-reference-properties"></a>Projeden projeye başvuru özellikleri

Aşağıdaki özellikler, **Başvurular** bölmesinde seçilen projeden projeden *projeye başvurusunu* aynı çözümdeki başka bir projeye tanımlar. Daha fazla bilgi için bkz. [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

- **Bağlantı kitaplığı bağımlılıkları**

   Bu özellik **true** olduğunda, proje sistemi, bağımsız PROJENIN oluşturduğu LIB dosyalarını bağımlı proje ile bağlar. Genellikle, **doğru değerini** belirtmeniz gerekir.

- **Proje tanımlayıcısı**

   Bağımsız projeyi benzersiz şekilde tanımlar. Özellik değeri, değiştirilebilir olmayan bir iç sistem GUID 'sidir.

- **Kitaplık Bağımlılığı Girişlerini Kullan**

   Bu özellik **false** olduğunda, proje sistemi bağımsız projenin oluşturduğu kitaplık dosyalarını bağımlı proje olarak bağmaz. Bu değer, artımlı bağlamayı devre dışı bırakır. Genellikle, birden çok bağımsız projenin olması halinde uygulamanın oluşturulması uzun zaman sürebileceğinden **yanlış değerini** belirtirsiniz.

### <a name="read-only-reference-properties-com--net"></a>Salt okuma başvuru özellikleri (COM & .NET)

Aşağıdaki özellikler COM ve .NET derleme başvurularında mevcuttur ve değiştirilebilir değildir.

- **Bütünleştirilmiş kod adı**

   Başvurulan derleme için derleme adını görüntüler.

- **Kültür**

   Seçili başvurunun kültürünü görüntüler.

- **Açıklama**

   Seçili başvurunun açıklamasını görüntüler.

- **Tam Yol**

   Başvurulan derlemenin dizin yolunu görüntüler.

- **Kimlik**

   .NET Framework derlemeleri için tam yolu görüntüler. COM bileşenleri için GUID 'yi görüntüler.

- **Etiketle**

   Başvurunun etiketini görüntüler.

- **Ad**

   Başvurunun adını görüntüler.

- **Ortak anahtar belirteci**

   Başvurulan derlemeyi tanımlamak için kullanılan ortak anahtar belirtecini görüntüler.

- **Tanımlayıcı ad**

   **`true`** başvurulan derlemenin tanımlayıcı bir adı varsa. Tanımlayıcı bir adlandırılmış derlemenin benzersiz bir sürümü vardır.

- **Sürüm**

   Başvurulan derlemenin sürümünü görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özellik sayfası başvurusu](reference/property-pages-visual-cpp.md)<br>
[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](working-with-project-properties.md)
