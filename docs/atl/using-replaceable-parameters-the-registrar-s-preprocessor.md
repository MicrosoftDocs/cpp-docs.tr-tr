---
title: "Değiştirilebilir parametreler (ATL Kaydedicisi) kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AddReplacement
- ClearReplacements
dev_langs:
- C++
helpviewer_keywords:
- '%MODULE%'
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b06333ba51b74501f3b7cd68248e5fb7e51ca94f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-replaceable-parameters-the-registrar39s-preprocessor"></a>Değiştirilebilir parametreler (kayıt &#39; s önişlemci) kullanma
Değiştirilebilir parametreler çalışma zamanı verileri belirtmek bir kayıt şirketinizin istemci izin verin. Bunu yapmak için kayıt şirketi içine komut değiştirilebilir parametreler ile ilişkili değerleri girer değiştirme harita tutar. Kayıt şirketi bu girişler çalışma zamanında yapar.  
  
##  <a name="_atl_using_.25.module.25"></a>MODÜL % kullanma  
 [ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md) kullanan bir komut dosyası otomatik olarak oluşturur `%MODULE%`. ATL bu parametredir sunucunuzun DLL veya EXE gerçek konumu için kullanır.  
  
## <a name="concatenating-run-time-data-with-script-data"></a>Çalışma zamanı verilerine komut dosyası verilerini birleştirme  
 Başka bir önişlemci betik verilerle çalışma zamanı verileri birleştirmek için kullanılır. Örneğin, bir giriş gerekirse dize sahip bir modül tam yolunu içeren varsayalım "`, 1`" sonuna. İlk olarak, aşağıdaki genişletme tanımlayın:  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Ardından, önce çağırma listelenen yöntemleri işleme betik birini [çağırma betikleri](../atl/invoking-scripts.md), eşlemeye yenisini ekleyin:  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/cpp/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 Komut dosyasının ayrıştırılırken kayıt şirketi genişletir `'%MODULE%, 1'` için `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  Kaydedici komut dosyasında, en büyük simge boyutu 4K'dır. (Bir belirteç herhangi tanınabilir sözdiziminde öğedir.) Bu, oluşturulan veya önişlemci tarafından Genişletilmiş belirteçleri içerir.  
  
> [!NOTE]
>  Çalışma zamanında değiştirme değeri değiştirmek için komut dosyasına çağrı kaldırın. [DECLARE_REGISTRY_RESOURCE](../atl/reference/registry-macros.md#declare_registry_resource) veya [DECLARE_REGISTRY_RESOURCEID](../atl/reference/registry-macros.md#declare_registry_resourceid) makrosu. Bunun yerine, kendi değiştirmek `UpdateRegistry` çağıran yöntemi [CAtlModule::UpdateRegistryFromResourceD](../atl/reference/catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](../atl/reference/catlmodule-class.md#updateregistryfromresources)ve ,dizigeçirin**_ATL_REGMAP_ENTRY** yapıları. Dizi **_ATL_REGMAP_ENTRY** ayarlamak için en az bir giriş olmalıdır {**NULL**,**NULL**}, bu girdi her zaman en son giriş olması gerekir. Aksi durumda, bir erişim ihlali hata olur oluşturulan **UpdateRegistryFromResource** olarak adlandırılır.  
  
> [!NOTE]
>  Yürütülebilir bir dosya çıkarır projesi oluştururken, ATL ile çalışma zamanında oluşturulan yol adını tırnak işaretleri içine otomatik olarak ekler. **MODÜL %** Kaydedici betik parametresi. Yol adı tırnak işaretleri dahil etmek istemiyorsanız, yeni kullanmak **MODULE_RAW %** parametre yerine.  
>   
>  DLL çıkarır projesi oluştururken, ATL tırnak işaretleri yol adı, eklemez **MODÜL %** veya **MODULE_RAW %** kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)

