---
title: Gecikmeli yüklenen DLL için tüm içe aktarmaları yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f054479a6681ba6de57690295fe3ce9f6c83696
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme
**__Hrloadallımportsfordll** delayhlp.cpp içinde tanımlanan işlevi söyler DLL'den ile belirtilen tüm içe aktarmaları yüklemek için bağlayıcı [/delayload](../../build/reference/delayload-delay-load-import.md) bağlayıcı seçeneği.  
  
 Tüm içe aktarmaları yükleme hata kodunuzda tek bir yerde işleme koyun ve özel durum içeri aktarmalar gerçek çağrıları geçici işleme kullanmak zorunda kalmazsınız izin verir. Burada, uygulamanızın kısmen alma yüklenmezse yardımcı kodu sonucunda bir işlemle kopması durumu ortadan kaldırır.  
  
 Çağırma **__hrloadallımportsfordll** kancaları ve hata davranışını değiştirmez; bkz [hata işleme ve bildirim](../../build/reference/error-handling-and-notification.md) daha fazla bilgi için.  
  
 DLL adı geçirilen **__hrloadallımportsfordll** DLL içinde depolanan adı ile karşılaştırılır ve büyük küçük harfe duyarlıdır.  
  
 Aşağıdaki örnekte nasıl çağrılacağını gösterir **__hrloadallımportsfordll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)