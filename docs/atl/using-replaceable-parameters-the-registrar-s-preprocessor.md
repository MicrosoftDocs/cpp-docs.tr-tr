---
title: Değiştirilebilir parametreler (ATL Kaydedicisi) kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 1c772c0493b351d8452400a4fb1e3949ab6f28f2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814039"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Değiştirilebilir parametreler kullanma (kayıt şirketi&#39;s önişlemci)

Değiştirilebilir parametreler, çalışma zamanı verileri belirtmek bir kayıt şirketinin istemci izin verin. Bunu yapmak için kayıt şirketi, betiğiniz içine değiştirilebilir parametreler ile ilişkili değerler girer değiştirme harita tutar. Kayıt şirketi, çalışma zamanında bu girişleri hale getirir.

##  <a name="_atl_using_.25.module.25"></a> MODÜL % kullanma

[ATL denetimi Sihirbazı](../atl/reference/atl-control-wizard.md) otomatik olarak kullanan bir komut dosyası oluşturduğu `%MODULE%`. ATL bu parametredir sunucunuzun DLL veya EXE gerçek konumu için kullanır.

## <a name="concatenating-run-time-data-with-script-data"></a>Betik verilerini ile çalışma zamanı verileri birleştirme

Başka bir önişlemci betik verilerini çalışma zamanı verilerle birleştirmek için kullanılır. Örneğin, bir giriş dizesiyle bir modül tam yolunu içeren gereklidir varsayalım "`, 1`" sonuna eklenir. İlk olarak, aşağıdaki genişletme tanımlayın:

```
'MySampleKey' = s '%MODULE%, 1'
```

Ardından, çağırmadan önce listelenen yöntemleri işleme betiği birini [çağırma betikleri](../atl/invoking-scripts.md), yerini haritaya eklemek:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

Komut dosyası ayrıştırılırken kayıt şirketi genişletir `'%MODULE%, 1'` için `c:\mycode\mydll.dll, 1`.

> [!NOTE]
>  Bir kaydedici betikte belirteci boyutu 4K olan. (Bir belirteç sözdizimi tanınan herhangi bir öğenin içindir.) Bu, oluşturulan veya önişlemci tarafından Genişletilmiş belirteçleri içerir.

> [!NOTE]
>  Çalışma zamanında değiştirme değeri yerine koymak istediğiniz komut dosyasına çağrısını kaldırın. [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) makrosu. Bunun yerine, kendi değerlerinizle değiştirin `UpdateRegistry` metoduna çağrı yapan [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources)ve _ATL_REGMAP_, dizi geçirin Giriş yapılar. {NULL, NULL} kümesi en az bir giriş _ATL_REGMAP_ENTRY, dizi olması gerekir ve bu giriş, her zaman en son giriş olmalıdır. Aksi takdirde, bir erişim ihlali hata olacaktır oluşturulan `UpdateRegistryFromResource` çağrılır.

> [!NOTE]
>  Yürütülebilir bir dosya çıkarır bir proje derlenirken, ATL ile çalışma zamanında oluşturulan yol adının etrafında tırnak işareti otomatik olarak ekler. **MODÜLÜ %** Kaydedici betik parametresi. Yol adı tırnak işaretleri dahil etmek istemiyorsanız, yeni kullanın **MODULE_RAW %** parametresi yerine.
>
>  Bir DLL çıkaran bir proje derlenirken, ATL tırnak işaretleri yol adını ekler değil **MODÜLÜ %** veya **MODULE_RAW %** kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)
