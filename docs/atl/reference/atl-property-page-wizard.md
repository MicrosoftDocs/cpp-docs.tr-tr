---
title: ATL Özellik Sayfası Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 671cb2fa19d920b0e60acd8d34623a05fe4a048e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703801"
---
# <a name="atl-property-page-wizard"></a>ATL Özellik Sayfası Sihirbazı

Bu sihirbaz [bir ATL projesine bir özellik sayfası ekler](../../atl/reference/adding-an-atl-property-page.md) veya MFC projesinde ATL desteği. ATL özellik sayfası özelliklerini ayarlamak için bir kullanıcı arabirimi sağlar (veya çağırma yöntemleri) bir veya daha fazla COM nesneleri.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2008'den itibaren bu sihirbaz tarafından üretilen kayıt betiği altında COM bileşenlerini kaydolacak **HKEY_CURRENT_USER** yerine **HKEY_LOCAL_MACHINE**. Bu davranışı değiştirmek için Ayarla **tüm kullanıcılar için kayıt bileşeni** ATL Sihirbazı seçeneği.

## <a name="names"></a>Adlar

Nesne, arabirimi ve projenize eklenecek sınıfların adlarını belirtin. Dışında **kısa ad**, bağımsız olarak tüm kutuları düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfadaki tüm diğer kutularının adlarını olarak yansıtılır. Değiştirirseniz **coclass'ı** ad değişikliği COM bölümünde yansıtılır **türü** ve **ProgID** kutuları. Bu adlandırma davranışı, özellik sayfası geliştirirken tüm adlarını kolayca tanımlanabilen yapmak için tasarlanmıştır.

> [!NOTE]
>  **Coclass'ı** nonattributed projelerine yalnızca düzenlenebilir. Projenizi öznitelikli, düzenleyemezsiniz **coclass'ı**.

### <a name="c"></a>C++

Nesne uygulamak için oluşturulan C++ sınıfına ilişkin bilgi sağlar.

|||
|-|-|
|Terim|Tanım|
|**Kısa ad**|Nesnenin kısaltılmış adını ayarlar. Sınıfı, sağladığınız ada belirler ve **coclass'ı** dosyasını adlandırır (**.cpp** ve **.h**) adlarını **türü** yanısıraadı **ProgID**, bu alanları ayrı ayrı değiştirmediğiniz sürece.|
|**.h dosyası**|Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.<br /><br /> Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.|
|**Sınıfı**|Nesne uygulayan sınıfın adını ayarlar. Bu ad, sağladığınız adına dayanarak **kısa ad**, 'C', tipik bir sınıf adı öneki öncesinde.|
|**.cpp dosyası**|Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız ada dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.<br /><br /> Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.|
|**Öznitelikli**|Nesne öznitelikleri kullanıp kullanmadığını belirtir. Yalnızca öznitelik atanmış ATL projesine nesne eklemek, bu seçenek kullanılırsa ve değiştirmek kullanılamaz, yani ekleyebileceğiniz nesneleri özniteliği desteği ile oluşturulan bir projeye öznitelikli.<br /><br /> Öznitelikli nesneyi kullanan öznitelikleri yalnızca bir ATL projesine ekleyebilirsiniz. Destek özniteliğine sahip bir ATL projesi için bu seçeneği belirlerseniz, Sihirbazı özniteliği destek projeye eklemek isteyip istemediğinizi belirtmenizi ister.<br /><br /> Varsayılan olarak, bu seçeneği belirledikten sonra eklediğiniz herhangi bir nesne öznitelikli olarak atanan (onay kutusu seçilidir). Öznitelikleri kullanmayan nesne eklemek için bu kutusunu temizleyebilirsiniz.<br /><br /> Bkz: [uygulama ayarları, ATL Proje Sihirbazı'nı](../../atl/reference/application-settings-atl-project-wizard.md) ve [öznitelikleri temel mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.|

### <a name="com"></a>COM

Nesne için COM işlevleri hakkında bilgi sağlar.

- **Coclass'ı**

   Nesne tarafından desteklenen arabirimlerin listesini içeren bileşen sınıfı adını ayarlar.

   > [!NOTE]
   > Öznitelikleri kullanarak projenizi oluşturmak ya da özellik sayfasını öznitelikleri kullanır Bu sihirbaz sayfasındaki gösteriyorsa, ATL içermez çünkü bu seçeneği değiştiremezsiniz `coclass` özniteliği.

- **Türü**

   Ayarlar kayıt defterinde görünür nesne açıklaması

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Özellik Sayfası Sihirbazı Seçenekleri](../../atl/reference/options-atl-property-page-wizard.md)   
[Dizeleri, ATL Özellik Sayfası Sihirbazı](../../atl/reference/strings-atl-property-page-wizard.md)   
[Örnek: Özellik Sayfası Uygulama](../../atl/example-implementing-a-property-page.md)

