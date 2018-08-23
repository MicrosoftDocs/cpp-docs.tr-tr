---
title: runtime_checks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
dev_langs:
- C++
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b20ea9dd12bfe4daff8e2e440c96a41c220aa742
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465713"
---
# <a name="runtimechecks"></a>runtime_checks
Devre dışı bırakır veya geri yükler [/RTC](../build/reference/rtc-run-time-error-checks.md) ayarları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Derleyici seçeneği ile etkin değil bir çalışma zamanı denetimi etkinleştirilemiyor. Örneğin, belirtmezseniz, `/RTCs`, belirten `#pragma runtime_checks( "s", restore)` yığın çerçeve doğrulama izin vermez.  
  
**Runtime_checks** pragma işlevin dışında görünmelidir ve pragma görüldüğünde sonra tanımlanmış konumundaki ilk işlev etkinleşir. *Geri* ve *kapalı* bağımsız değişkenleri kapatma seçenekleri belirtilen **runtime_checks** açıp kapatabilir.  
  
**Runtime_checks** sıfır veya daha fazla parametre aşağıdaki tabloda gösterilen olabilir.  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>Runtime_checks Pragması parametreleri  
  
|Parametre|Çalışma zamanı denetim türü|  
|--------------------|-----------------------------|  
|*s*|Etkinleştirir (çerçeve) doğrulama yığın.|  
|*c*|Veri kaybı ile sonuçlanır daha küçük bir veri türü için bir değer atandığında raporlar.|  
|*u*|Bir değişken tanımlanmadan kullanıldığında raporlar.|  
  
İle kullanılan aynı harflerini bunlar `/RTC` derleyici seçeneği. Örneğin:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
Kullanarak **runtime_checks** pragma ile boş bir dize (**""**) özel bir formu yönergesi:  
  
- Kullanırken *kapalı* parametresi, kapalı yukarıdaki tabloda listelenen çalışma zamanı hata denetimleri kapatır.  
  
- Kullanırken *geri* parametresi ile belirtilen bu çalışma zamanı hata denetimleri sıfırlar, `/RTC` derleyici seçeneği.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   