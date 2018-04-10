---
title: Gecikmeli yüklenen DLL için tüm içe aktarmaları yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8afa206e62702407d9974802f9422c8597d772ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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