---
title: "' % S'projesi (ATL Eğitmeni, bölüm 1) oluşturma | Microsoft Docs"
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54b45ff8c7af8c8aaf7232cefa2bb4f002fc37be
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755624"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Proje Oluşturma (ATL Eğitmeni, Bölüm 1)

Bu öğreticide, bir Çokgen görüntüleyen bir ActiveX nesnesini oluşturan bir nonattributed ATL projesi adım adım açıklanmaktadır. Nesne Çokgen ve kod görünümü yenileyin yapmasını kenar sayısını değiştirmek için kullanıcı vermeye yönelik seçenekler içerir.

> [!NOTE]
>  ATL ve MFC genellikle Visual Studio'nun Express sürümlerinde desteklenmez.

> [!NOTE]
>  Bu öğreticide, aynı kaynak kodunun Çokgen örnek olarak oluşturulur. Kaynak Kodu el ile girmekten kaçınmak istiyorsanız, buradan indirebilirsiniz [Çokgen örnek soyut](../visual-cpp-samples.md). Öğreticide iş ya da kendi projenizi hataları denetlemek için kullanmak gibi Çokgen kaynak koduna ardından başvurabilir.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL projesi Sihirbazı'nı kullanarak ilk ATL projesi oluşturmak için

1. Visual Studio geliştirme ortamında tıklayın **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.

2. Tıklayın **Visual C++ projeleri** klasörü ve select **ATL projesi**.

3. Tür *Çokgen* proje adı.

     Kaynak kodu için konum My Documents\Visual Studio projeleri için genellikle varsayılan olur ve yeni bir klasör otomatik olarak oluşturulur.

4. Tıklayın **Tamam** ve ATL projesi Sihirbazı'nı açar.

5. Tıklayın **uygulama ayarları** kullanılabilir seçenekleri görmek için.

6. Bir denetim oluşturuyorsanız ve bir işlem sunucusu bir denetim olmalıdır gibi bırakın **uygulama türü** bir DLL olarak.

7. Diğer seçenekleri varsayılan değerlerinde bırakın ve tıklayın **son**.

ATL projesi Sihirbazı projeyi birkaç dosya oluşturarak oluşturun. Çokgen nesne genişleterek, bu dosyaları Çözüm Gezgini'nde görüntüleyebilirsiniz. Dosya aşağıda listelenmiştir.

|Dosya|Açıklama|
|----------|-----------------|
|Polygon.cpp|Uygulamasını içerir `DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, ve `DllUnregisterServer`. Ayrıca, projenizdeki ATL nesnelerin listesi olan nesne eşlemesine içerir. Başlangıçta boş budur.|
|Polygon.def|Bu modül tanım dosyası, bağlayıcı, DLL tarafından gerekli dışarı aktarma hakkında bilgi sağlar.|
|Polygon.idl|Nesnelerinizi belirli arabirimleri açıklar arabirimi tanım dili dosyası.|
|Polygon.rgs|Bu kayıt defteri betik programınızın DLL kaydetmeye yönelik bilgileri içerir.|
|Polygon.rc|Kaynak dosyası başlangıçta sürüm bilgilerini ve proje adını içeren bir dize içerir.|
|Kaynak.h|Kaynak dosyası için üst bilgi dosyası.|
|Polygonps.def|Bu modül tanım dosyası, bağlayıcı çağrıları apartmanlar arasında destekleyen proxy ve saplama kod tarafından gerekli dışarı aktarmaları hakkında bilgi sağlar.|
|stdafx.cpp|Bu dosyanın `#include` ATL uygulama dosyaları.|
|stdafx.h|Bu dosyanın `#include` ATL üstbilgi dosyalarını.|

1. Çözüm Gezgini'nde sağ `Polygon` proje.

2. Kısayol menüsünde **özellikleri**.

3. Tıklayarak **bağlayıcı**. Değişiklik **UserRedirection başına** seçeneğini **Evet**.

4. **Tamam**'ı tıklatın.

Sonraki adımda, projenize bir denetim ekleyeceksiniz.

[Adım 2](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Öğretici](../atl/active-template-library-atl-tutorial.md)
