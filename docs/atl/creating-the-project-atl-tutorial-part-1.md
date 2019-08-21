---
title: Proje Oluşturma (ATL Eğitmeni, Bölüm 1)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: 9f7f62ec94d5ac6d6076763853aa19297cf310e6
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630699"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Proje Oluşturma (ATL Eğitmeni, Bölüm 1)

Bu öğretici, bir çokgen görüntüleyen ActiveX nesnesi oluşturan, öznitelikli bir ATL projesinde adım adım yönergeler sunar. Nesnesi, kullanıcının çokgeni oluşturan kenar sayısını değiştirmesine izin verme ve görüntüyü yenilemek için kod içerir.

> [!NOTE]
> ATL ve MFC, Visual Studio 'nun Express sürümlerinde genellikle desteklenmez.

> [!NOTE]
> Bu öğretici, çokgen örneğiyle aynı kaynak kodu oluşturur. Kaynak kodu el ile girmekten kaçınmak isterseniz, [Çokgen örnek soyut](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon)' ndan indirebilirsiniz. Daha sonra öğreticide çalışırken Çokgen kaynak koduna başvurabilir veya kendi projenizdeki hataları denetlemek için bunu kullanabilirsiniz.
> Derlemek için, *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) öğesini açın ve değiştirin:
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
> örneklerini şununla değiştirin:
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
> Derleyici, doğru bir şekilde `regsvr32` çıkmadığımızı hala şikayet eder, ancak Denetim dll 'inin hala kullanılabilir ve kullanıma hazır olması gerekir.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL Proje Sihirbazı 'Nı kullanarak ilk ATL projesini oluşturmak için

1. Visual Studio 2017 ve önceki sürümlerde: **Dosya** > yeniProje > . **Görsel C++**  sekmesini açın ve **MFC/ATL**' yi seçin. **ATL projesi**seçin.

   Visual Studio 2019: **Dosya** > **Yeni**proje ' yi seçin, arama kutusuna "ATL" yazın ve ATL projesi ' ni seçin. > 

1. Proje adı olarak *Çokgen* yazın.

    Kaynak kodun konumu genellikle varsayılan olarak \Users\\\<Kullanıcı adı > \source\depoları ' dir ve yeni bir klasör otomatik olarak oluşturulur.

1. Visual Studio 2019 ' de, varsayılan değerleri kabul edin ve **Tamam**' ı tıklatın. 
   Visual Studio 2017 ' de, **atl Proje** Sihirbazı ' nı açmak için **Tamam** ' ı tıklatın. Kullanılabilir seçenekleri görmek için **uygulama ayarları** ' na tıklayın. Bu proje bir denetim oluşturduğundan ve bir denetimin işlem içi sunucu olması gerektiğinden, **uygulama türünü** dll olarak bırakın. **Tamam**'ı tıklatın.

Visual Studio, birden çok dosya oluşturarak projeyi oluşturur. `Polygon` Nesneyi genişleterek bu dosyaları **Çözüm Gezgini** görüntüleyebilirsiniz. Dosyalar aşağıda listelenmiştir.

::: moniker range="<=vs-2017"

|Dosya|Açıklama|
|----------|-----------------|
|Çokgen. cpp|`DllMain`, ,,`DllCanUnloadNow`Ve uygulamasınıiçerir`DllUnregisterServer`. `DllGetClassObject` `DllRegisterServer` Ayrıca, projenizdeki ATL nesnelerinin bir listesi olan nesne eşlemesini içerir. Bu başlangıçta boştur.|
|Çokgen. def|Bu modül tanımı dosyası bağlayıcı için gerekli olan dışarı aktarmalar hakkında bilgi sağlar.|
|Çokgen. IDL|Nesneleriniz için özel arabirimleri açıklayan arabirim tanımlama dili dosyası.|
|Çokgen. rgs|Bu kayıt defteri betiği, programınızın DLL 'sini kaydetme bilgilerini içerir.|
|Çokgen. RC|Başlangıçta sürüm bilgilerini içeren kaynak dosyası ve proje adını içeren bir dize.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|Polygonps. def|Bu modül tanımı dosyası, bağlayıcıya, apartmanlar genelinde çağrıları destekleyen proxy ve saplama kodu için gereken dışarı aktarmalar hakkındaki bilgileri sağlar.|
|stdafx.cpp|`#include` *Stbafx. h*olacak dosya.|
|stdafx.h|ATL üstbilgi dosyalarını yapılacak `#include` ve ön derleyen dosya.|

::: moniker-end

::: moniker range=">=vs-2019"

|Dosya|Açıklama|
|----------|-----------------|
|Çokgen. cpp|`DllMain`, ,,`DllCanUnloadNow`Ve uygulamasınıiçerir`DllUnregisterServer`. `DllGetClassObject` `DllRegisterServer` Ayrıca, projenizdeki ATL nesnelerinin bir listesi olan nesne eşlemesini içerir. Bu başlangıçta boştur.|
|Çokgen. def|Bu modül tanımı dosyası bağlayıcı için gerekli olan dışarı aktarmalar hakkında bilgi sağlar.|
|Çokgen. IDL|Nesneleriniz için özel arabirimleri açıklayan arabirim tanımlama dili dosyası.|
|Çokgen. rgs|Bu kayıt defteri betiği, programınızın DLL 'sini kaydetme bilgilerini içerir.|
|Çokgen. RC|Başlangıçta sürüm bilgilerini içeren kaynak dosyası ve proje adını içeren bir dize.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|Polygonps. def|Bu modül tanımı dosyası, bağlayıcıya, apartmanlar genelinde çağrıları destekleyen proxy ve saplama kodu için gereken dışarı aktarmalar hakkındaki bilgileri sağlar.|
|PCH. cpp|*Pch. h*olacak `#include` dosya.|
|PCH. h|ATL üstbilgi dosyalarını yapılacak `#include` ve ön derleyen dosya.|

::: moniker-end

1. **Çözüm Gezgini**, `Polygon` projeye sağ tıklayın.

1. Kısayol menüsünde, **Özellikler**' e tıklayın.

1. **Bağlayıcı**' ya tıklayın. **Kullanıcı başına yeniden yönlendirme** seçeneğini **Evet**olarak değiştirin.

1. **Tamam**'ı tıklatın.

Bir sonraki adımda projenize bir denetim ekleyeceksiniz.

[2. adım](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
