---
title: kısıtlama (C++ AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758862d5296cf0a51cc0e04d849b044b3694e087
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461894"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
Kısıtlama tanımlayıcısı işlev ve lambda bildirimlerine uygulanabilir. C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı kullanan uygulamalarda işlevdeki kod ve işlevin davranışı için kısıtlamalar uygular.  
  
> [!NOTE]
>  Hakkında bilgi için **kısıtlama** parçası olan anahtar sözcüğü **__declspec** depolama sınıfı öznitelikleri [kısıtlama](../cpp/restrict.md).  
  
 **Kısıtlama** yan tümcesi aşağıdaki biçimleri alır:  
  
|Yan Tümce|Açıklama|  
|------------|-----------------|  
|`restrict(cpu)`|İşlev tam C++ dilini kullanabilir. İşlevi yalnızca restrict(cpu) işlevleri kullanılarak bildirilen diğer işlevler çağırabilir.|  
|`restrict(amp)`|İşlev, yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kümesini kullanabilir.|  
|Bir `restrict(cpu)` ve `restrict(amp)` dizisi.|İşlev hem `restrict(cpu)` hem de `restrict(amp)` kısıtlamalarına uymalıdır. İşlev, `restrict(cpu)`,  `restrict(amp)`, `restrict(cpu, amp)` veya `restrict(amp, cpu)` kullanılarak bildirilen işlevler tarafından çağrılabilir.<br /><br /> `restrict(A) restrict(B)` biçimi `restrict(A,B)` olarak yazılabilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 **Kısıtlama** anahtar sözcüğü bağlamsal bir sözcüktür. Kısıtlama tanımlayıcıları `cpu` ve `amp`, ayrılmış sözcükler değildir. Tanımlayıcıların listesi genişletilemez. Sahip olmayan bir işlev bir **kısıtlama** yan tümcesi olan bir işlev ile aynı ise `restrict(cpu)` yan tümcesi.  
  
 `restrict(amp)` yan tümcesine sahip bir işlev aşağıdaki kısıtlamalara sahiptir:  
  
-   İşlev yalnızca `restrict(amp)` yan tümcesine sahip işlevleri çağırabilir.  
  
-   İşlev satır içine alınabilir olmalıdır.  
  
-   İşlevi yalnızca bildirebilirsiniz **int**, **işaretsiz int**, **float**, ve **çift** değişkenleri, sınıf ve yalnızca içeren yapıları Bu tür. **bool** da izin verilir, ancak bir bileşen türünde kullanıyorsanız 4 bayt hizalı olmalıdır.  
  
-   Lambda işlevleri, başvuruya göre yakalama gerçekleştiremez ve işaretçileri yakalayamaz.  
  
-   Başvurular ve tek yöneltmeli işaretçiler, yalnızca yerel değişkenler, işlev bağımsız değişkenleri ve dönüş türleri olarak desteklenir.  
  
-   Aşağıdakilere izin verilmez:  
  
    -   Yineleme.  
  
    -   Değişkenleri [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü.  
  
    -   Sanal işlevler.  
  
    -   İşlev işaretçileri.  
  
    -   Üye işlevlerinin işaretçileri.  
  
    -   Yapılar içerisindeki işaretçiler.  
  
    -   İşaretçilerin işaretçileri.  
  
    -   **goto** deyimleri.  
  
    -   Etiketli deyimler.  
  
    -   **deneyin**, **catch**, veya **throw** deyimleri.  
  
    -   Genel değişkenler.  
  
    -   Statik değişkenler. Kullanım [tile_static anahtar sözcüğü](../cpp/tile-static-keyword.md) yerine.  
  
    -   **dynamic_cast** yayınlar.  
  
    -   **TypeID** işleci.  
  
    -   asm bildirimleri.  
  
    -   Varargs.  
  
 İşlev kısıtlamaları için bkz [restrict(amp) kısıtlamaları](http://go.microsoft.com/fwlink/p/?LinkId=251089).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `restrict(amp)`yan tümcesi.  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)