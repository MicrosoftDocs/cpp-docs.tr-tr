---
title: ATL Özellik Sayfası Sihirbazı
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.class.atl.ppg.overview
helpviewer_keywords:
- ATL projects, adding property pages
- ATL Property Page Wizard
ms.assetid: 6113e325-facd-4f68-b491-144d75209922
ms.openlocfilehash: 791901ab3181ad2c8ac862a970980250693d20f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248239"
---
# <a name="atl-property-page-wizard"></a>ATL Özellik Sayfası Sihirbazı

Bu sihirbaz [bir ATL projesine bir özellik sayfası ekler](../../atl/reference/adding-an-atl-property-page.md) veya MFC projesinde ATL desteği. ATL özellik sayfası özelliklerini ayarlamak için bir kullanıcı arabirimi sağlar (veya çağırma yöntemleri) bir veya daha fazla COM nesneleri.

> [!WARNING]
> Visual Studio 2017 sürüm 15.9 bu kod Sihirbazı kullanım dışıdır ve Visual Studio'nun gelecekteki bir sürümde kaldırılacak. Bu sihirbaz nadiren kullanılır. ATL ve MFC genel desteği, bu sihirbazın kaldırma işlemi etkilenmez. Bu kullanımdan kaldırma hakkındaki görüşlerinizi paylaşmak istiyorsanız, Lütfen tamamlayın [bu anketi](https://www.surveymonkey.com/r/QDWKKCN). Geri bildiriminiz bizim için önemlidir.

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

- **Tür**

   Ayarlar kayıt defterinde görünür nesne açıklaması

- **ProgID**

   Kapsayıcı nesnesinin CLSID yerine kullanabileceği adını ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Özellik Sayfası Sihirbazı Seçenekleri](../../atl/reference/options-atl-property-page-wizard.md)<br/>
[Dizeleri, ATL Özellik Sayfası Sihirbazı](../../atl/reference/strings-atl-property-page-wizard.md)<br/>
[Örnek: Özellik sayfası uygulama](../../atl/example-implementing-a-property-page.md)
