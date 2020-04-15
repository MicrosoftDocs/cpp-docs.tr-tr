---
title: Değiştirilebilir Parametreleri Kullanma (ATL Registrar)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 2474db2de384baa9113ed39aef4d3d9c9048903d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329226"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Değiştirilebilir Parametreleri Kullanma (Kayıt Şirketi&#39;Önİşlemci)

Değiştirilebilir parametreler, kayıt şirketinin istemcisinin çalışma zamanı verilerini belirtmesine olanak sağlar. Bunu yapmak için, Kayıt Şirketi komut dosyanızdaki değiştirilebilir parametrelerle ilişkili değerleri girdiği yedek bir eşeği tutar. Kayıt Şirketi bu girişleri çalışma zamanında yapar.

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a>%MODÜL% kullanma

[ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md) otomatik olarak kullanan `%MODULE%`bir komut dosyası oluşturur. ATL, sunucunuzun DLL veya EXE'sinin gerçek konumu için bu değiştirilebilir parametreyi kullanır.

## <a name="concatenating-run-time-data-with-script-data"></a>Çalışma Zamanı Verilerini Komut Dosyası Verileriyle Zayıflatma

Önişlemcinin bir diğer kullanımı da çalışma zamanı verilerini komut dosyası verileriyle birleştirmektir. Örneğin, sonunda eklenen " "`, 1`dizeli bir modüle tam bir yol içeren bir giriş gerektiğini varsayalım. İlk olarak, aşağıdaki genişletme tanımlayın:

```
'MySampleKey' = s '%MODULE%, 1'
```

Ardından, [Komut Dosyalarını Çağırma'da](../atl/invoking-scripts.md)listelenen komut dosyası işleme yöntemlerinden birini çağırmadan önce, haritaya bir yedek ekleyin:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

Komut dosyasının ayrışması sırasında, Kayıt `'%MODULE%, 1'` Defteri `c:\mycode\mydll.dll, 1`.

> [!NOTE]
> Registrar komut dosyasında, 4K en yüksek belirteç boyutudur. (Belirteç sözdiziminde tanınabilir bir öğedir.) Bu, önişlemci tarafından oluşturulan veya genişletilmiş belirteçleri içerir.

> [!NOTE]
> Çalışma zamanında değiştirme değerlerini değiştirmek için, komut dosyasındaki çağrıyı [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) makroya kaldırın. Bunun yerine, CAtlModule çağıran kendi `UpdateRegistry` yöntemi ile değiştirin::UpdateRegistryFromResourceD veya [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources), ve _ATL_REGMAP_ENTRY yapıları dizi geçmek. [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) _ATL_REGMAP_ENTRY dizinizin {NULL,NULL} olarak ayarlanmış en az bir girişi olmalıdır ve bu giriş her zaman son giriş olmalıdır. Aksi takdirde, çağrıldığında `UpdateRegistryFromResource` bir erişim ihlali hatası oluşturulur.

> [!NOTE]
> Yürütülebilir çıktıları olan bir proje oluşturulurken, ATL **%MODULE%** kayıt defteri komut dosyası parametresi ile çalışma zamanında oluşturulan yol adının etrafına otomatik olarak teklif işaretleri ekler. Yol adının tırnak işaretlerini içermesini istemiyorsanız, bunun yerine yeni **%MODULE_RAW parametreyi** kullanın.
>
> DLL çıktısı veren bir proje inşa ederken, **%MODÜL%veya** **%MODULE_RAW%** kullanılırsa, ATL yol adına teklif işaretleri eklemez.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Defteri Komut Dosyaları Oluşturma](../atl/creating-registrar-scripts.md)
