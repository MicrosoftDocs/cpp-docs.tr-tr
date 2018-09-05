---
title: -sdl (ek güvenlik denetimlerini etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
dev_langs:
- C++
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6f88e254a49309c0ca44c330fdc71d32ee1a87d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686345"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (Ek Güvenlik Denetimlerini Etkinleştir)
Önerilen güvenlik geliştirme yaşam döngüsü (SDL) denetimleri ekler. Bu denetimler, hatalar ve ek güvenli kod oluşturma özellikleri olarak güvenlikle ilgili ek uyarıları içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/sdl[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ SDL** şunun tarafından sağlanan temel güvenlik denetimleri üst kümesi sağlayan [/GS](../../build/reference/gs-buffer-security-check.md) ve geçersiz kılmaları **/GS-**. Varsayılan olarak, **/SDL** kapalıdır. **Değerlendirme** ek güvenlik denetimlerini devre dışı bırakır.  
  
## <a name="compile-time-checks"></a>Derleme zamanı denetimleri  
 **/ SDL** bu uyarıları hata olarak sağlar:  
  
|/ SDL tarafından etkin uyarı|Eşdeğer komut satırı anahtarı|Açıklama|  
|------------------------------|-------------------------------------|-----------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|Bir birli eksi işleci işaretsiz bir sonuç elde edilen bir işaretsiz türe uygulandı.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|Bir negatif tamsayı sabiti işaretsiz türe, büyük olasılıkla anlamsız sonucunda elde edilen dönüştürülür.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|Kullanım `continue`, `break` veya `goto` anahtar bir `__finally` / `finally` blok olağan dışı sonlandırma sırasında davranışı tanımsız.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|Bir değişken başlatma kod yürütülmez.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|Başlatılmamış bir yerel değişken kullanın.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|Başlatılmayabilecek yerel işaretleyici değişken kullanımı.|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|Belirli C çalışma zamanı (CRT) işlevleri kullanıldığında taşması.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Bir işlev kullanımını pragma ile işaretlenmiş [kullanım dışı](../../preprocessor/deprecated-c-cpp.md).|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|Olarak işaretlenmiş bir işlevinin [kullanım dışı](../../cpp/deprecated-cpp.md).|  
  
## <a name="runtime-checks"></a>Çalışma zamanı denetimleri  
 Zaman **/SDL** olan etkin, derleyici çalışma zamanında bu denetimleri gerçekleştirmek için kod oluşturur:  
  
-   Katı modu sağlar **/GS** çalışma zamanı arabellek taşması algılama, ile derleme için eşdeğer `#pragma strict_gs_check(push, on)`.  
  
-   Sınırlı işaretçi temizleme gerçekleştirir. Değil içeren ifadeler başvurusunu kaldırır ve hiçbir kullanıcı tanımlı bir yıkıcıya sahip türler, çağrısı yapıldıktan sonra geçerli olmayan bir adrese işaretçi başvuruları ayarlanır `delete`. Yeniden kullanılması engellenen eski işaretçi başvuruları yardımcı olur.  
  
-   Sınıf üye başlatma gerçekleştirir. Tüm sınıf üyeleri (oluşturucu döngülerinden önce) nesne örneklemesini sıfır otomatik olarak başlatır. Bu oluşturucu açıkça başlatılmaz sınıf üyeleri ile ilişkilendirilmiş başlatılmamış veri kullanımını engeller.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [uyarıları, / SDL ve değişken başlatılmamış algılama geliştirme](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/).  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Üzerinde **genel** sayfasında, ilgili seçeneği seçin **SDL denetimleri** aşağı açılan listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)