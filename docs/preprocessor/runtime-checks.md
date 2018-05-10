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
ms.openlocfilehash: 817afaff738b2528bd165e814517c8399cd8a151
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="runtimechecks"></a>runtime_checks
Devre dışı bırakır veya geri yükler [eş yordamlarla/RTC](../build/reference/rtc-run-time-error-checks.md) ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyici seçeneği ile etkin değil bir çalışma zamanı denetimi etkinleştiremezsiniz. Örneğin, /RTCs belirtmezseniz belirten `#pragma runtime_checks( "s", restore)` yığın çerçeve doğrulama izin vermez.  
  
 **Runtime_checks** pragma dışında bir işlev görünmesi gerekir ve pragma görülen sonra tanımlanan ilk işlevi etkili olur. **Geri** ve **devre dışı** bağımsız değişkenleri kapatma belirtilen seçenekler *runtime_checks* açıp kapatma.  
  
 *Runtime_checks* sıfır veya daha çok parametrelerden biri aşağıdaki tabloda gösterilen olabilir.  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>Runtime_checks Pragması parametreleri  
  
|Parametre|Çalışma zamanında denetim türü|  
|--------------------|-----------------------------|  
|**s**|Etkinleştirir (çerçeve) doğrulama yığın.|  
|**c**|Veri kaybı ile sonuçlanır daha küçük bir veri türü için bir değer atandığında raporlar.|  
|**u**|Bir değişken tanımlanmadan önce kullanıldığında raporlar.|  
  
 Eş yordamlarla/RTC derleyici seçeneği ile kullanılan aynı harf bunlar. Örneğin:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 Kullanarak **runtime_checks** boş dize ile pragma (**""**) yönergesi özel şekildedir:  
  
-   Kullandığınızda **kapalı** parametresi, kapalı yukarıdaki tabloda listelenen çalışma zamanı hata denetimleri açar.  
  
-   Kullandığınızda **geri** parametresi, eş yordamlarla/RTC derleyici seçeneği ile belirtilen olanlar için çalışma zamanı hata denetimleri sıfırlar.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
