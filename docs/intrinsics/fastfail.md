---
title: __fastfail | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efdd067376d8e1430ed8636c0a77afe950858e9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fastfail"></a>__fastfail
**Microsoft özel**  
  
 Hemen en az yük ile arama işlemi sonlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __fastfail(unsigned int code);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`code`  
 A `FAST_FAIL_<description>` winnt.h veya işlem sonlandırma nedeni gösterir wdm.h sembolik sabiti.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `__fastfail` İç döndürmez.  
  
## <a name="remarks"></a>Açıklamalar  
 `__fastfail` İç bir mekanizma sağlar bir *hızlı başarısız* isteği — isteği hemen işlem sonlandırma için olası bozuk bir işlem için bir yol. Program durumu ve kurtarma ötesinde yığın bozulmuş olabilir kritik hataları tesis normal özel durum işleme tarafından işlenemez. Kullanım `__fastfail` en az ek yükü kullanarak işlem sonlandırılacak.  
  
 Dahili olarak, `__fastfail` birkaç mimarisi özgü mekanizmalarını kullanarak uygulanır:  
  
|Mimari|Yönergesi|Kod bağımsız değişkeni konumu|  
|------------------|-----------------|-------------------------------|  
|x86|int 0x29|ecx|  
|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|int 0x29|RCX|  
|ARM|Opcode 0xDEFB|r0|  
  
 Bir hızlı başarısız istek birbirinden bağımsızdır ve genellikle yürütmek için yalnızca iki yönergeleri gerektirir. Hızlı başarısız istek yürütüldükten sonra çekirdek sonra uygun tedbiri alır. Kullanıcı modu kodda bellek bağımlılıklar yoktur yönerge işaretçisi ötesinde hızlı başarısız olay oluşturulduğunda. Ciddi Bellek Bozulması olsa bile bu ve güvenilirliği en üst düzeye çıkarır.  
  
 `code` Bağımsız değişkeni — birini `FAST_FAIL_<description>` winnt.h veya wdm.h—describes hata koşul türünü sembolik sabitler ve hata raporları bir ortama özgü şekilde eklenmiştir.  
  
 Kullanıcı modu hızlı başarısız istekleri ikinci bir fırsat devam ettirilebilir olmayan özel durum özel durum kodu 0xC0000409 ile en az bir özel durum parametresi olarak görünür. İlk özel durum parametresi `code` değeri. Windows hata bildirimi (WER) ve işlem bozuk ve en az işlem içi Eylemler hatası için yanıt alınıp alınmayacağını hata ayıklama altyapısı bu özel durum kodu gösterir. Çekirdek modu hızlı başarısız istekleri, bir özel hata denetimi kodu kullanarak uygulanır `KERNEL_SECURITY_CHECK_FAILURE` (0x139). Program bozuk bir durumda olması bekleniyor çünkü her iki durumda da, hiçbir özel durum işleyicileri çağrılır. Bir hata ayıklayıcısı varsa, sona ermeden önce programın durumunu incelemek için bir fırsat verildi.  
  
 Yerel hızlı başarısız mekanizması desteği, Windows 8'de başlamıştır. Hızlı başarısız yönerge yerel olarak desteklemeyen bir Windows işletim sistemleri genellikle kabul hızlı başarısız istek bir erişim ihlali olarak veya bir `UNEXPECTED_KERNEL_MODE_TRAP` hata denetimi. Bu durumlarda, hala sonlandırılan olmasa da hızlı bir şekilde programdır.  
  
 `__fastfail`yalnızca bir iç kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__fastfail`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)], ARM|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)