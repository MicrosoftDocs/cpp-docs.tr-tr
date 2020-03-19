---
title: Proje Oluşturma (ATL Eğitmeni, Bölüm 1)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: b4c18d83feb6c61b603bb1880960193cf9150f9b
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79509401"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Proje Oluşturma (ATL Eğitmeni, Bölüm 1)

Bu öğretici, bir çokgen görüntüleyen ActiveX nesnesi oluşturan, öznitelikli bir ATL projesinde adım adım yönergeler sunar. Nesnesi, kullanıcının çokgeni oluşturan kenar sayısını değiştirmesine izin verme ve görüntüyü yenilemek için kod içerir.

> [!NOTE]
> Bu öğretici, çokgen örneğiyle aynı kaynak kodu oluşturur. Kaynak kodu el ile girmekten kaçınmak isterseniz, [Çokgen örnek soyut](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon)' ndan indirebilirsiniz. Daha sonra öğreticide çalışırken Çokgen kaynak koduna başvurabilir veya kendi projenizdeki hataları denetlemek için bunu kullanabilirsiniz.
> Derlemek için, *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) öğesini açın ve değiştirin:
>
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
>
> şununla değiştirin
>
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
>
> Derleyici, doğru bir şekilde çıkmadan `regsvr32` şikayet eder, ancak hala denetimin DLL 'inin oluşturulup kullanılabilmesi için kullanılabilir.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL Proje Sihirbazı 'Nı kullanarak ilk ATL projesini oluşturmak için

1. Visual Studio 2017 ve önceki sürümlerde: **dosya** > **Yeni** > **projesi**. **Görsel C++**  sekmesini açın ve **MFC/ATL**' yi seçin. **ATL projesi**seçin.

   Visual Studio 2019: **dosya** > **Yeni** > **Proje**' yi seçin, arama kutusuna "ATL" yazın ve **ATL projesi**' ni seçin.

1. Proje adı olarak *Çokgen* yazın.

    Kaynak kodun konumu genellikle varsayılan olarak \Users\\\<username > \source\repos olarak değişir ve yeni bir klasör otomatik olarak oluşturulur.

1. Visual Studio 2019 ' de, varsayılan değerleri kabul edin ve **Tamam**' ı tıklatın. 
   Visual Studio 2017 ' de, **atl Proje** Sihirbazı ' nı açmak için **Tamam** ' ı tıklatın. Kullanılabilir seçenekleri görmek için **uygulama ayarları** ' na tıklayın. Bu proje bir denetim oluşturduğundan ve bir denetimin işlem içi sunucu olması gerektiğinden, **uygulama türünü** dll olarak bırakın. **Tamam** düğmesine tıklayın.

Visual Studio, birden çok dosya oluşturarak projeyi oluşturur. `Polygon` nesnesini genişleterek bu dosyaları **Çözüm Gezgini** görüntüleyebilirsiniz. Dosyalar aşağıda listelenmiştir.

::: moniker range="<=vs-2017"

|Dosya|Açıklama|
|----------|-----------------|
|Çokgen. cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`ve `DllUnregisterServer`uygulamasını içerir. Ayrıca, projenizdeki ATL nesnelerinin bir listesi olan nesne eşlemesini içerir. Bu başlangıçta boştur.|
|Çokgen. def|Bu modül tanımı dosyası bağlayıcı için gerekli olan dışarı aktarmalar hakkında bilgi sağlar.|
|Çokgen. IDL|Nesneleriniz için özel arabirimleri açıklayan arabirim tanımlama dili dosyası.|
|Çokgen. rgs|Bu kayıt defteri betiği, programınızın DLL 'sini kaydetme bilgilerini içerir.|
|Çokgen. RC|Başlangıçta sürüm bilgilerini içeren kaynak dosyası ve proje adını içeren bir dize.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|Polygonps. def|Bu modül tanımı dosyası, bağlayıcıya, apartmanlar genelinde çağrıları destekleyen proxy ve saplama kodu için gereken dışarı aktarmalar hakkındaki bilgileri sağlar.|
|stdafx.cpp|*Stbafx. h*`#include` olacak dosya.|
|stdafx.h|ATL üstbilgi dosyalarını `#include` ve ön derleyen dosya.|

::: moniker-end

::: moniker range=">=vs-2019"

|Dosya|Açıklama|
|----------|-----------------|
|Çokgen. cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`ve `DllUnregisterServer`uygulamasını içerir. Ayrıca, projenizdeki ATL nesnelerinin bir listesi olan nesne eşlemesini içerir. Bu başlangıçta boştur.|
|Çokgen. def|Bu modül tanımı dosyası bağlayıcı için gerekli olan dışarı aktarmalar hakkında bilgi sağlar.|
|Çokgen. IDL|Nesneleriniz için özel arabirimleri açıklayan arabirim tanımlama dili dosyası.|
|Çokgen. rgs|Bu kayıt defteri betiği, programınızın DLL 'sini kaydetme bilgilerini içerir.|
|Çokgen. RC|Başlangıçta sürüm bilgilerini içeren kaynak dosyası ve proje adını içeren bir dize.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|Polygonps. def|Bu modül tanımı dosyası, bağlayıcıya, apartmanlar genelinde çağrıları destekleyen proxy ve saplama kodu için gereken dışarı aktarmalar hakkındaki bilgileri sağlar.|
|PCH. cpp|`#include` *pch. h*olacak dosya.|
|PCH. h|ATL üstbilgi dosyalarını `#include` ve ön derleyen dosya.|

::: moniker-end

1. **Çözüm Gezgini**, `Polygon` projesine sağ tıklayın.

1. Kısayol menüsünde, **Özellikler**' e tıklayın.

1. **Bağlayıcı**' ya tıklayın. **Kullanıcı başına yeniden yönlendirme** seçeneğini **Evet**olarak değiştirin.

1. **Tamam** düğmesine tıklayın.

Bir sonraki adımda projenize bir denetim ekleyeceksiniz.

[2. adım](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
