---
description: 'Daha fazla bilgi edinin: değiştirilebilir parametreler kullanma (kayıt&#39;'
title: Değiştirilebilen parametreleri kullanma (ATL kaydedici)
ms.date: 11/04/2016
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
ms.openlocfilehash: 5b8b8071115186a462bbf9ca0b12d869458dd925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157208"
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Değiştirilebilen parametreleri kullanma (kaydedici&#39;s Önişlemci)

Değiştirilebilen parametreler, bir kaydedici istemcisinin çalışma zamanı verilerini belirtmesini sağlar. Bunu yapmak için, kaydedici, betiğinizdeki değiştirilebilen parametrelerle ilişkili değerleri girdiği bir değiştirme haritası sağlar. Kaydedici bu girişleri çalışma zamanında yapar.

## <a name="using-module"></a><a name="_atl_using_.25.module.25"></a> % MODULE% kullanılıyor

[Atl Denetim Sihirbazı](../atl/reference/atl-control-wizard.md) tarafından kullanılan bir betiği otomatik olarak oluşturur `%MODULE%` . ATL, sunucunuzun DLL veya EXE 'sinin gerçek konumu için bu değiştirilebilir parametreyi kullanır.

## <a name="concatenating-run-time-data-with-script-data"></a>Betik verileriyle Run-Time verileri bitiştirme

Önişlemci 'nin başka bir kullanımı, çalışma zamanı verilerini betik verileriyle birleştirmek için kullanılır. Örneğin, sonuna "" dizesinin bulunduğu bir modülün tam yolunu içeren bir girdinin gerekli olduğunu varsayalım `, 1` . İlk olarak, aşağıdaki genişletmeyi tanımlayın:

```rgs
'MySampleKey' = s '%MODULE%, 1'
```

Ardından, [betikleri çağırma](../atl/invoking-scripts.md)bölümünde listelenen betik işleme yöntemlerinden birini çağırmadan önce haritaya bir değiştirme ekleyin:

[!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]

Betiği ayrıştırma sırasında, kaydedici `'%MODULE%, 1'` öğesine genişletilir `c:\mycode\mydll.dll, 1` .

> [!NOTE]
> Bir kaydedici betiğinde, 4K en büyük belirteç boyutudur. (Belirteç söz diziminde tanınabilir bir öğedir.) Bu, Önişlemci tarafından oluşturulan veya genişletilen belirteçleri içerir.

> [!NOTE]
> Çalışma zamanında değiştirme değerlerini değiştirmek için, betikteki çağrıyı [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) makrosuna kaldırın. Bunun yerine, bunu, `UpdateRegistry` [CAtlModule:: UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule:: UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources)' ı çağıran kendi yönteinkini ile değiştirin ve _ATL_REGMAP_ENTRY yapıları dizinizi geçirin. _ATL_REGMAP_ENTRY dizinizin {NULL, NULL} olarak ayarlanmış en az bir girişi olmalıdır ve bu giriş her zaman son giriş olmalıdır. Aksi takdirde, çağrıldığında bir erişim ihlali hatası oluşturulur `UpdateRegistryFromResource` .

> [!NOTE]
> Yürütülebilir bir dosya çıkaran bir proje oluştururken, ATL otomatik olarak çalışma zamanında oluşturulan yol adının çevresine **% module%** kaydedici betik parametresiyle birlikte tırnak işareti ekler. Yol adının tırnak işaretlerini içermesini istemiyorsanız, bunun yerine yeni **% MODULE_RAW%** parametresini kullanın.
>
> DLL çıktısını veren bir proje oluştururken, **% module%** veya **% MODULE_RAW%** kullanılırsa, ATL yol adına tırnak işareti eklemez.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
