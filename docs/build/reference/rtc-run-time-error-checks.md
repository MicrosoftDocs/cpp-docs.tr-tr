---
title: -RTC (çalışma zamanı hata denetimleri) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
dev_langs:
- C++
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a135c9c4e32ea7a54c45719eff503ff99509d3e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378463"
---
# <a name="rtc-run-time-error-checks"></a>/RTC (Çalışma Zamanı Hata Denetimleri)
Etkinleştirmek ve çalışma zamanı hata denetimleri özelliği ile birlikte devre dışı bırakmak için kullanılan [runtime_checks](../../preprocessor/runtime-checks.md) pragması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## <a name="arguments"></a>Arguments  
 `1`  
 Karşılığıdır **eş yordamlarla/RTC**`su`.  
  
 `c`  
 Raporları bir değer atanması küçük bir veri türü ve veri kaybı sonuçlanır. Örneğin, bir değer türü `short 0x101` türündeki bir değişkene atanır `char`.  
  
 Bu seçenek, amaçladığınız truncate, örneğin, ilk sekiz bitleri istiyorsanız durumlarda raporları bir `int` olarak döndürülen bir `char`. Çünkü **eş yordamlarla/RTC** `c` bir çalışma zamanı hatası neden olan herhangi bir bilgi atama sonucunda kaybolursa, bir çalışma zamanı hatası sonucu olarak önlemek için gereken bilgileri kapalı maskeleyebilirsiniz **eş yordamlarla/RTC** `c`. Örneğin:  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 Etkinleştirir çerçevesi çalışma zamanı hatası, aşağıdaki gibi yığın denetim:  
  
-   Sıfır olmayan bir değer yerel değişkenleri başlatma. Bu hata ayıklama modunda çalışırken görünmez hataları belirlemenize yardımcı olur. Yığın değişkenlerini sıfır yayın derlemesi yığını değişkenleri derleyici iyileştirmesi nedeniyle yayın derlemesi için karşılaştırıldığında hata ayıklama derlemesi içinde hala olur büyük bir fırsat yok. Bir program kullanılan bir alanı kendi yığınının sonra derleyici tarafından hiçbir zaman 0 olarak sıfırlanır. Bu nedenle, aynı yığın alanı kullanmak için durum sonraki, başlatılmamış yığın değişkenlerini Bu yığın belleği önceki kullanımdan kalan değerler geri dönebilirsiniz.  
  
-   Aşırı çalıştırmaları ve dizi gibi yerel değişkenler underruns algılanması. **/ RTC** `s` taşmaları derleyici doldurma bir yapı içinde oluşur bellek erişirken algılamaz. Doldurma kullanarak oluşabilir [Hizala](../../cpp/align-cpp.md), [/Zp (yapı üyesi hizalama)](../../build/reference/zp-struct-member-alignment.md), veya [paketi](../../preprocessor/pack.md), veya yapı öğeleri doldurma eklemek için derleyici gerektiren konusunda bir şekilde sipariş.  
  
-   Yığın işaretçi Bozulması algılar yığını işaretçi doğrulama. Yığın işaretçi Bozulması arama kuralı uyuşmazlığı nedeniyle oluşabilir. Örneğin, bir işlev işaretçisi kullanarak, bir işlevi olarak dışa aktarılan dll çağırma [__stdcall](../../cpp/stdcall.md) ancak olarak işlev işaretçisi bildirme [__cdecl](../../cpp/cdecl.md).  
  
 `u`  
 Bir değişken başlatılmamış olmadan kullanıldığında, raporlar. Örneğin, oluşturan yönerge `C4701` altında bir çalışma zamanı hata de oluşturabilir **eş yordamlarla/RTC**`u`. Oluşturur yönerge [Derleyici Uyarısı (düzey 1 ve düzey 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) altında bir çalışma zamanı hatası oluşturur **eş yordamlarla/RTC**`u`.  
  
 Ancak, aşağıdaki kod parçası göz önünde bulundurun:  
  
```cpp  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 Bir değişken başlatılmış, onu tarafından çalışma zamanında raporlanmayacaktır **eş yordamlarla/RTC**`u`. Örneğin, Select işaretçi üzerinden değişkenidir sonra derleyici değil değişkeni izlemek ve rapor başlatılmamış kullanır. Geçerli bir değişken adresini gerçekleştirerek başlatabilirsiniz. & Bu durumda bir atama işleci gibi işleci çalışır.  
  
## <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı hata denetimleri, çalışan kodunuzda sorunları bulmak bir yöntemdir; Daha fazla bilgi için bkz: [nasıl yapılır: çalışma zamanı kullanmak yerel denetler](/visualstudio/debugger/how-to-use-native-run-time-checks).  
  
 Programınızı herhangi birini kullanarak komut satırında derleme yaparsanız **eş yordamlarla/RTC** derleyici seçenekleri, tüm pragma [en iyi duruma getirme](../../preprocessor/optimize.md) kodunuzu'ndaki yönergeleri sessizce başarısız olur. Çalışma zamanı hata denetimleri (en iyi duruma getirilmiş) yayın derlemesi geçerli olmayan olmasıdır.  
  
 Kullanmanız gereken **eş yordamlarla/RTC** geliştirme derlemeleri; **Eş yordamlarla/RTC** perakende derleme için kullanılmamalıdır. **/ RTC** derleyici iyileştirmeler etkinleştirilerek kullanılamaz ([/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)). Bir programın görüntü ile oluşturulan **eş yordamlarla/RTC** biraz daha büyük ve göre biraz ile yerleşik bir görüntü daha yavaş olacaktır **/Od** (en fazla yüzde 5 daha yavaş bir **/Od** yapı).  
  
 Kullandığınızda __msvc_runtıme_checks önişlemci yönergesi tanımlanan **eş yordamlarla/RTC** seçeneği veya [/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **kod oluşturma** özellik sayfası.  
  
4.  Birini veya her ikisini aşağıdaki özellikleri değiştirin: **temel çalışma zamanı denetler** veya **küçük türü denetimi**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> özellikleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks)