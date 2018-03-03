---
title: "(C++ AMP) kısıtlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60ac40e2cb64c307574d14c1f7cc7a5290c740ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
Kısıtlama tanımlayıcısı işlev ve lambda bildirimlerine uygulanabilir. C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı kullanan uygulamalarda işlevdeki kod ve işlevin davranışı için kısıtlamalar uygular.  
  
> [!NOTE]
>  Hakkında bilgi için `restrict` parçası olan anahtar sözcük `__declspec` depolama sınıfı öznitelikler bkz [kısıtlamak](../cpp/restrict.md).  
  
 `restrict` yan tümcesi aşağıdaki biçimleri alır:  
  
|Yan Tümce|Açıklama|  
|------------|-----------------|  
|`restrict(cpu)`|İşlev tam C++ dilini kullanabilir. İşlevi yalnızca restrict(cpu) işlevleri kullanılarak bildirilen diğer işlevler çağırabilir.|  
|`restrict(amp)`|İşlev, yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kümesini kullanabilir.|  
|Bir `restrict(cpu)` ve `restrict(amp)` dizisi.|İşlev hem `restrict(cpu)` hem de `restrict(amp)` kısıtlamalarına uymalıdır. İşlev, `restrict(cpu)`,  `restrict(amp)`, `restrict(cpu, amp)` veya `restrict(amp, cpu)` kullanılarak bildirilen işlevler tarafından çağrılabilir.<br /><br /> `restrict(A) restrict(B)` biçimi `restrict(A,B)` olarak yazılabilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `restrict` anahtar sözcüğü bağlamsal bir anahtar sözcüktür. Kısıtlama tanımlayıcıları `cpu` ve `amp`, ayrılmış sözcükler değildir. Tanımlayıcıların listesi genişletilemez. `restrict` yan tümcesi olmayan bir işlev, `restrict(cpu)` yan tümcesine sahip işlevle aynıdır.  
  
 `restrict(amp)` yan tümcesine sahip bir işlev aşağıdaki kısıtlamalara sahiptir:  
  
-   İşlev yalnızca `restrict(amp)` yan tümcesine sahip işlevleri çağırabilir.  
  
-   İşlev satır içine alınabilir olmalıdır.  
  
-   İşlev yalnızca `int`, `unsigned int`, `float` ve `double` değişkenlerini ve yalnızca bu türleri içeren sınıfları ve yapıları bildirebilir. `bool`'a da izin verilir, ancak bir bileşen türünde kullanıyorsanız 4 bayt hizalı olması gerekir.  
  
-   Lambda işlevleri, başvuruya göre yakalama gerçekleştiremez ve işaretçileri yakalayamaz.  
  
-   Başvurular ve tek yöneltmeli işaretçiler, yalnızca yerel değişkenler, işlev bağımsız değişkenleri ve dönüş türleri olarak desteklenir.  
  
-   Aşağıdakilere izin verilmez:  
  
    -   Yineleme.  
  
    -   İle bildirilen değişkenlerin [volatile](../cpp/volatile-cpp.md) anahtar sözcüğü.  
  
    -   Sanal işlevler.  
  
    -   İşlev işaretçileri.  
  
    -   Üye işlevlerinin işaretçileri.  
  
    -   Yapılar içerisindeki işaretçiler.  
  
    -   İşaretçilerin işaretçileri.  
  
    -   `goto` deyimleri.  
  
    -   Etiketli deyimler.  
  
    -   `try`, `catch` veya `throw` deyimleri.  
  
    -   Genel değişkenler.  
  
    -   Statik değişkenler. Kullanım [tile_static anahtar sözcüğü](../cpp/tile-static-keyword.md) yerine.  
  
    -   `dynamic_cast` atamaları.  
  
    -   `typeid` işleci.  
  
    -   asm bildirimleri.  
  
    -   Varargs.  
  
 Bir işlev kısıtlamaları tartışma için bkz: [restrict(amp) kısıtlamaları](http://go.microsoft.com/fwlink/p/?LinkId=251089).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `restrict(amp)`yan tümcesi.  
  
```  
  
void functionAmp() restrict(amp) {}   
void functionNonAmp() {}   
  
void callFunctions() restrict(amp)   
{   
    // int is allowed.  
    int x;  
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.  
    // long long int y;   
  
    // Calling an amp-restricted function is allowed.  
    functionAmp();   
  
    // Calling a non-amp-restricted function is not allowed.  
    // functionNonAmp();   
  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)