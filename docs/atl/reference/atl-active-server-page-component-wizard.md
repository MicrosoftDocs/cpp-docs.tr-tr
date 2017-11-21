---
title: "ATL Active Server sayfası Bileşen Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.asp.overview
dev_langs: C++
helpviewer_keywords:
- ASP components, creating in ATL
- ATL Active Server Page Component Wizard
ms.assetid: 5a5cb904-dbbf-44ea-ad3d-2ddd14c1d3c5
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 021740039044a43972cb51390ecf5cc1babdafe1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-active-server-page-component-wizard"></a>ATL Active Server sayfası Bileşen Sihirbazı
Bu sihirbaz, bir Active Server Pages (ASP) bileşeni projeye ekler. Microsoft Internet Information Services (IIS), ASP bileşenleri geliştirilmiş Web sayfası geliştirme mimarisinin bir parçası olarak kullanır.  
  
 Bu sihirbazı kullanarak, modeli ve toplama desteğini bileşenin iş parçacığı belirtebilirsiniz. Hata bilgisi arabirimi, bağlantı noktaları ve ücretsiz iş parçacıklı hazırlama desteği de belirtebilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betik COM bileşenlerini altında kaydedeceksiniz **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için ayarlanmış **kayıt bileşeni tüm kullanıcılar için** ATL Sihirbazı'nın seçeneği.  
  
## <a name="names"></a>Adlar  
 Nesne, arabirim ve projenize eklemek için sınıflar için adlarını belirtin. Dışında **kısa ad**, diğer tüm kutularının bağımsız olarak diğer düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını yansıtılır.  
  
 Değiştirirseniz **Coclass** COM bölümünde değişiklik adını yansıtılır **türü** ve **ProgID** kutuları, ancak **arabirimi** adı değiştirmez. Bu adlandırma davranış denetiminizi geliştirdikçe tüm adlar kolayca tanımlanabilen yapmak için tasarlanmıştır.  
  
### <a name="c"></a>C++  
 Nesne için oluşturulan C++ sınıfı için bilgiler sağlar.  
  
 **Kısa ad**  
 Nesne için kök ad ayarlar. Belirler sağladığınız ad `Class` ve **Coclass** adları, **.cpp dosya** ve **.h dosyası** adları, **arabirim**adı **türü** adları ve **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.  
  
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
  
 Destek özniteliğine sahip bir ATL projesi için bu seçeneği seçerseniz, Sihirbazı özniteliği desteği projeye eklemek isteyip istemediğinizi belirtmek için ister.  
  
 Varsayılan olarak, nonattributed projeleri için bu seçeneği belirledikten sonra eklediğiniz tüm nesnelerin öznitelikli olarak atanmış (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutuyu temizleyebilirsiniz.  
  
 Bkz: [uygulama ayarları, ATL Proje Sihirbazı](../../atl/reference/application-settings-atl-project-wizard.md) ve [temel öznitelikleri mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.  
  
### <a name="com"></a>COM  
 Nesne için COM işlevleri hakkında bilgi sağlar.  
  
 **Coclass'ı**  
 Nesne tarafından desteklenen arabirimleri listesini içeren bileşen sınıfı adını ayarlar. Projenizi veya bu nesne öznitelikleri kullanıyorsa, ATL içermemesi bu seçeneği değiştiremezsiniz **coclass** özniteliği.  
  
 **Türü**  
 Coclass'ı için kayıt defterinde görünür nesne açıklaması ayarlar.  
  
 **Arabirimi**  
 Nesne için oluşturduğunuz arabirimi ayarlar. Bu arabirim, özel yöntemler içerir.  
  
 **ProgID**  
 Kapsayıcı nesne CLSID yerine kullanabileceğiniz adını ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Active Server sayfası bileşeni](../../atl/reference/adding-an-atl-active-server-page-component.md)

