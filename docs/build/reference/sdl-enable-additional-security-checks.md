---
title: "-sdl (ek güvenlik denetimlerini etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
dev_langs:
- C++
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5cbcb74272fa7cae3dd0c641bd6371c8f0f9c204
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (Ek Güvenlik Denetimlerini Etkinleştir)
Önerilen güvenlik geliştirme yaşam döngüsü (SDL) denetimler de ekler. Bu denetimler, ek güvenlik ilgili uyarıları hatalar ve ek güvenli kod oluşturma özellikleri olarak içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/sdl[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ SDL** tarafından sağlanan temel güvenlik denetimlerini bir alt kümesi sağlayan [/GS](../../build/reference/gs-buffer-security-check.md) ve geçersiz kılmalar **/GS-**. Varsayılan olarak, **/SDL** kapalıdır. **/SDL-** ek güvenlik denetimleri devre dışı bırakır.  
  
## <a name="compile-time-checks"></a>Derleme zamanı denetimleri  
 **/ SDL** bu uyarıları hata olarak sağlar:  
  
|/ SDL tarafından etkin uyarı|Eşdeğer komut satırı anahtarı|Açıklama|  
|------------------------------|-------------------------------------|-----------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|Birli işleç eksi imzasız sonucunda elde edilen bir işaretsiz tür uygulandı.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|İşaretsiz tür, büyük olasılıkla anlamsız sonucunda elde edilen negatif bir tam sayı sabit dönüştürülür.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|Kullanımı `continue`, `break` veya `goto` anahtar bir `__finally` / `finally` blok davranışı anormal sonlandırma sırasında tanımlanmamış.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|Bir değişken başlatma kodu çalıştırılmayacak.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|Başlatılmamış bir yerel değişken kullanın.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|Potansiyel olarak başlatılmamış yerel işaretçi değişkeninin kullanın.|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|Belirli C çalışma zamanı (CRT) işlevlerini kullanıldığında taşması.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|İşlevinin kullanımı pragma ile işaretlenmiş [kullanım dışı](../../preprocessor/deprecated-c-cpp.md).|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|İşlevinin kullanımı olarak işaretli [kullanım dışı](../../cpp/deprecated-cpp.md).|  
  
## <a name="runtime-checks"></a>Çalışma zamanı denetimleri  
 Zaman **/SDL** olduğu etkin derleyici çalışma zamanında bu denetimleri gerçekleştirmek için kod oluşturur:  
  
-   Katı modunu etkinleştirir **/GS** çalışma zamanı arabellek taşması algılama, ile derleme için eşdeğer `#pragma strict_gs_check(push, on)`.  
  
-   Sınırlı işaretçi temizleme işlemi gerçekleştirir. Değil içeren ifadelerde dereferences ve hiçbir kullanıcı tarafından tanımlanan yıkıcı sahip türlerinde, çağrısı yapıldıktan sonra geçerli olmayan bir adrese işaretçi başvuruları ayarlanır `delete`. Bu, eski işaretçi başvuruları kullanılmasını önlemeye yardımcı olur.  
  
-   Sınıf üyesi başlatma gerçekleştirir. Nesne örneklemesi (önce Oluşturucusu çalışır) sıfır sınıf üyelerinin tamamı otomatik olarak başlatır. Bu oluşturucu açıkça başlatılmaz sınıfı üyeleriyle ilişkilendirilmiş başlatılmamış verilerin kullanımını engeller.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [uyarıları, / SDL ve başlatılmamış değişken algılama geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=331012).  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Üzerinde **genel** sayfasında, ilgili seçeneği seçin **SDL denetimleri** aşağı açılan liste.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)