---
title: Proje (ATL Eğitmeni, bölüm 1) oluşturma | Microsoft Docs
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
ms.openlocfilehash: 1aedf7b4112d4c8d4bb5b2a174e93925f5a46ce5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357724"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Proje Oluşturma (ATL Eğitmeni, Bölüm 1)
Bu öğreticide Çokgen görüntüleyen bir ActiveX nesnesi oluşturan bir nonattributed ATL project aracılığıyla adım adım açıklanmaktadır. Nesne görünümü yenilemek için Çokgen ve kod hale kenarların sayısını değiştirmek için kullanıcı izin vermek için seçenekleri içerir.  
  
> [!NOTE]
>  ATL ve MFC genellikle Visual Studio Express sürümleri desteklenmez.  
  
> [!NOTE]
>  Bu öğretici Çokgen örnek aynı kaynak kodunu oluşturur. Kaynak Kodu el ile girmeyi önlemek istiyorsanız, buradan indirebilirsiniz [Çokgen örnek Özet](../visual-cpp-samples.md). Öğreticide iş ya da kendi projedeki hatalarını denetlemek için kullanmak gibi Çokgen kaynak koduna sonra başvurabilirsiniz.  
  
### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL Proje Sihirbazı'nı kullanarak ilk ATL projesi oluşturmak için  
  
1.  Visual Studio geliştirme ortamında tıklatın **yeni** üzerinde **dosya** menüsüne ve ardından **proje**.  
  
2.  Tıklatın **Visual C++ projeleri** klasörü ve select **ATL Proje**.  
  
3.  Tür `Polygon` proje adı olarak.  
  
     Kaynak kodu konumunu My Documents\Visual Studio projelerine genellikle varsayılan ve yeni bir klasör otomatik olarak oluşturulur.  
  
4.  Tıklatın **Tamam** ve ATL Proje Sihirbazı'nı açar.  
  
5.  Tıklatın **uygulama ayarları** kullanılabilir seçenekleri görmek için.  
  
6.  Bir denetim oluşturma ve bir denetim bir işlemdeki sunucu olmalıdır gibi bırakın **uygulama türü** DLL olarak.  
  
7.  Diğer seçenekleri varsayılan değerlerinde bırakın ve tıklayın **son**.  
  
 ATL Proje Sihirbazı çeşitli dosyaları oluşturarak projesi oluşturacaksınız. Çokgen nesne genişleterek, bu dosyaları Çözüm Gezgini'nde görüntüleyebilirsiniz. Dosyaları, aşağıda listelenmiştir.  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|Polygon.cpp|Uygulamasını içerir `DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, ve `DllUnregisterServer`. Ayrıca, projenize ATL nesneleri listesi nesne eşlemesi içerir. Bu başlangıçta boş olur.|  
|Polygon.def|Bu modül tanım dosyasını bağlayıcı DLL tarafından gerekli dışarı aktarma hakkında bilgi sağlar.|  
|Polygon.idl|Nesnelerinizi belirli arabirimleri tanımlayan arabirim tanımı dil dosyası.|  
|Polygon.rgs|Bu kayıt defteri komut dosyası programınızın DLL kaydetmeye yönelik bilgileri içerir.|  
|Polygon.rc|Kaynak dosyası başlangıçta sürüm bilgileri ve proje adı içeren bir dize içeriyor.|  
|Kaynak.h|Kaynak dosya için üstbilgi dosyası.|  
|Polygonps.def|Bu modül tanım dosyası bağlayıcı grupların çağrıları destekleyen proxy ve saplama kodla gerekli dışarı aktarma hakkında bilgi sağlar.|  
|stdafx.cpp|Olur dosya `#include` ATL uygulama dosyaları.|  
|stdafx.h|Olur dosya `#include` ATL üstbilgi dosyaları.|  
  
1.  Çözüm Gezgini'nde sağ `Polygon` projesi.  
  
2.  Kısayol menüsünde **özellikleri**.  
  
3.  Tıklayın **bağlayıcı**. Değişiklik **UserRedirection başına** için seçenek **Evet**.  
  
4.  **Tamam**'ı tıklatın.  
  
 Sonraki adımda, projeniz için bir denetim ekleyeceksiniz.  
  
 [2. adım açın](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici](../atl/active-template-library-atl-tutorial.md)

