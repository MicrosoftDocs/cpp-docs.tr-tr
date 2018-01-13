---
title: "ATL Basit Nesne Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.simple.overview
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding objects
- ATL Simple Object Wizard
ms.assetid: f7f85741-9aad-4543-a917-a29b996364da
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cbefa4a8036802599dd97f31d57f18204fd6104f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı
Bu sihirbaz projeye en az bir COM nesnesi ekler. Sihirbazın bu sayfası nesneniz ve COM işlevselliği için dosyaları ve C++ sınıfı tanımlamak adlarını belirtmek için kullanın.  
  
 Kullanım [seçenekleri](../../atl/reference/options-atl-simple-object-wizard.md) çift arabirimler ve Otomasyon destekleyip ve nesnenin iş parçacığı modeli, kendi toplama belirtmek için bu sihirbazın desteklemez. Hata bilgisi arabirimi, bağlantı noktaları, Internet Explorer Destek ve ücretsiz iş parçacıklı hazırlama için destek de belirtebilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betik COM bileşenlerini altında kaydedeceksiniz **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için ayarlanmış **kayıt bileşeni tüm kullanıcılar için** ATL Sihirbazı'nın seçeneği.  
  
## <a name="names"></a>Adlar  
 Nesne, arabirim ve projenize eklemek için sınıflar için adlarını belirtin. Dışında **kısa ad**, diğer tüm kutularının bağımsız olarak diğer düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını yansıtılır. Değiştirirseniz **Coclass** COM bölümünde değişiklik adını yansıtılır **türü** ve **ProgID** kutuları, ancak **arabirimi** adı değiştirmez. Bu adlandırma davranış denetiminizi geliştirdikçe tüm adlar kolayca tanımlanabilen yapmak için tasarlanmıştır.  
  
> [!NOTE]
>  **Coclass'ı** yalnızca nonattributed projelerde düzenlenebilir. Projenizi öznitelikli, düzenleyemezsiniz **coclass'ı**.  
  
## <a name="c"></a>C++  
 Nesne için oluşturulan C++ sınıfı için bilgiler sağlar.  
  
 **Kısa ad**  
 Nesne için kısa ad ayarlar. Belirler sağladığınız ad `Class` ve **Coclass** adları, **.cpp dosya** ve **.h dosyası** adları, **arabirim**adı **türü** adları ve **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.  
  
 **.h dosyası**  
 Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **Sınıfı**  
 Oluşturulacak sınıfın adını ayarlar. Bu ad, sağladığınız adına dayanarak **kısa ad**, öncesinde 'C', tipik bir sınıf adı öneki olarak.  
  
 **.cpp dosyası**  
 Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad sağladığınız adına dayalı **kısa ad**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **Öznitelikli**  
 Nesne öznitelikleri kullanıp kullanmadığını belirtir. Öznitelik atanmış ATL projesinde nesneyi ekliyorsanız, bu seçenek seçilen ve değiştirmek mevcut değil. Diğer bir deyişle, öznitelik desteği ile oluşturulan bir proje yalnızca öznitelikli nesneleri ekleyebilirsiniz.  
  
 Öznitelikli nesne öznitelikleri kullanan yalnızca bir ATL projesine ekleyebilirsiniz. Destek özniteliğine sahip bir ATL projesi için bu seçeneği seçerseniz, Sihirbazı özniteliği desteği projeye eklemek isteyip istemediğinizi belirtmek için ister.  
  
 Varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz tüm nesnelerin öznitelikli olarak atanmış (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutuyu temizleyebilirsiniz.  
  
 Bkz: [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [temel öznitelikleri mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.  
  
## <a name="com"></a>COM  
 Nesne için COM işlevleri hakkında bilgi sağlar.  
  
 **Coclass'ı**  
 Nesne tarafından desteklenen arabirimleri listesini içeren bileşen sınıfı adını ayarlar.  
  
> [!NOTE]
>  Öznitelikleri kullanarak projenizi oluşturmak ya da bu sihirbaz sayfasındaki nesne öznitelikleri kullandığını gösteriyorsa, ATL içermemesi bu seçeneği değiştiremezsiniz `coclass` özniteliği.  
  
 **Türü**  
 Kayıt defterinde görünür nesne açıklaması ayarlar  
  
 **Arabirimi**  
 Nesne için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.  
  
 **ProgID**  
 Kapsayıcı nesne CLSID yerine kullanabileceğiniz adını ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Basit Nesne](../../atl/reference/adding-an-atl-simple-object.md)

