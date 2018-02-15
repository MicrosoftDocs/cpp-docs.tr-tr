---
title: __security_init_cookie | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- __security_init_cookie
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c51e02a36df9a54d2f301eafc24a0181e97153f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="securityinitcookie"></a>__security_init_cookie
Genel güvenlik tanımlama bilgisi başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __security_init_cookie(void);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Genel güvenlik tanımlama bilgisi ile derlenmiş kod taşması koruma için kullanılan [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ve özel durum işleme kullanan kod. Giriş taşması korumalı işlevi için tanımlama bilgisi yığında yerleştirilir ve Çıkışta değerini yığında genel tanımlama bilgisi ile karşılaştırılır. Aralarındaki fark, bir arabellek taşması oluştu ve hemen programın sonlandırılması neden gösterir.  
  
 Normalde, `__security_init_cookie` başlatıldığında CRT tarafından çağrılır. CRT başlatma atlarsanız — Örneğin, kullanırsanız [/Entry](../../build/reference/entry-entry-point-symbol.md) giriş noktasını belirtmek için — çağırmalısınız sonra `__security_init_cookie` kendiniz. Varsa `__security_init_cookie` çağrılmaz, genel güvenlik tanımlama bilgisi, varsayılan bir değere ayarlanır ve arabellek taşması koruma riske. Bir saldırgan arabellek taşması denetimleri üstesinden gelmek için bu varsayılan tanımlama bilgisi değeri yararlanabilir her zaman çağrı öneririz `__security_init_cookie` tanımladığınızda, kendi giriş noktası.  
  
 Çağrı `__security_init_cookie` herhangi önce taşması korumalı hale getirilmesi gereken işlevi girilir; Aksi takdirde alacaklardır arabellek taşması algılanır. Daha fazla bilgi için bkz: [C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="example"></a>Örnek  
 Örneklere bakın [C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`__security_init_cookie`|\<Process.h >|  
  
 `__security_init_cookie` bir Microsoft Standart C çalışma zamanı kitaplığı uzantısıdır. Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Güvenlik derinlemesine denetler](http://go.microsoft.com/fwlink/p/?linkid=7260)