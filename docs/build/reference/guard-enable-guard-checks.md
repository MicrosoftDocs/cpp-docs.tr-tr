---
title: -GUARD (koruyucu denetimlerini etkinleştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d05dd4f9d213c3d2729459486a9d0cfdbd79110
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375262"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (Koruyucu Denetimlerini Etkinleştirme)
Denetim akışı koruyucu denetimlerini desteği yürütülebilir görüntüde belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GUARD:{CF|NO}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /GUARD:cf belirtildiğinde, bağlayıcı bir .dll veya .exe denetim akışı Guard (CFG) çalışma zamanı denetimleri için destek belirtmek için üstbilgisinin değiştirir. Bağlayıcı gerekli denetim akışı hedef adres verileri de üstbilgiye ekler. Varsayılan olarak, /GUARD:CF devre dışıdır. Bunu açıkça /GUARD:NO kullanarak devre dışı bırakılabilir. Etkili olması için /GUARD:CF de gerektirir [/DYNAMICBASE (adres boşluğu düzeni rastgele'seçimini kullan)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) varsayılan olarak açık bağlayıcı seçeneği.  
  
 Kaynak kodu zaman derlenmiş kullanarak [/guard:cf](../../build/reference/guard-enable-control-flow-guard.md) seçeneği, derleyici çözümler denetim akışı tüm dolaylı çağrıları olası hedef adresleri için inceleyerek. Derleyici hedef dolaylı çağrı yönerge bilinen hedef adresleri çalışma zamanında listesinde adresidir doğrulamak için kodu ekler. CFG Dur CFG çalışma zamanı başarısız bir program destekleyen işletim sistemleri denetleyin. Bu, arama hedefini değiştirmek için veri bozulması kullanarak kötü amaçlı kod yürütmek bir saldırganın zorlaştırır.  
  
 /GUARD:CF seçeneği derleyici ve bağlayıcı CFG etkin yürütülebilir görüntüler oluşturmak için belirtilmesi gerekir. Derlenmiş ancak /GUARD:CF kullanarak bağlantılı olmayan kod çalışma zamanı denetimleri maliyet oluşturur, ancak CFG koruma sağlamaz. İçin /GUARD:CF seçeneği belirtildiğinde `cl` derlemek ve tek bir adımda derleyici bağlamak için komut bağlayıcıya bayrağı geçirir. Zaman **denetim akışı koruma** özelliği, Visual Studio'da ayarlanmışsa, /GUARD:CF seçeneği derleyici ve bağlayıcı için geçirilir. Nesne dosyaları veya kitaplıkları ayrı olarak derlenmiştir zaman seçeneği açıkça belirtilmelidir `link` komutu.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **bağlayıcı**, **komut satırı**.  
  
3.  İçinde **ek seçenekler**, girin `/GUARD:CF`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Guard (etkinleştirmek denetim akışı koruma)](../../build/reference/guard-enable-control-flow-guard.md)   
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)