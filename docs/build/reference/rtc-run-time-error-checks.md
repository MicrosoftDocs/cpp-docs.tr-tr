---
title: /RTC (Çalışma Zamanı Hata Denetimleri)
ms.date: 11/04/2016
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
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
ms.openlocfilehash: a830ff5b8ba4b7fcd95eb462f899f2eadce6de11
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815898"
---
# <a name="rtc-run-time-error-checks"></a>/RTC (Çalışma Zamanı Hata Denetimleri)

Etkinleştirme ve birlikte çalışma zamanı hata denetimleri özelliği devre dışı bırakmak için kullanılan [runtime_checks](../../preprocessor/runtime-checks.md) pragması.

## <a name="syntax"></a>Sözdizimi

```
/RTC1
/RTCc
/RTCs
/RTCu
```

## <a name="arguments"></a>Arguments

**1**<br/>
Denk olan **/RTC**`su`.

**c**<br/>
Küçük bir veri türü ve veri kaybına raporları bir değer atanır. Örneğin, bir değer türü `short 0x101` türünde bir değişkene atanır `char`.

Bu seçenek, düşündüğünüz truncate, örneğin, ilk sekiz bitlik istiyorsanız durumlarda raporları bir `int` olarak döndürülen bir `char`. Çünkü **/RTC** `c` bir çalışma zamanı hatasına neden olur atamanın sonucu olarak bilgileri kaybolursa, sonucu olarak bir çalışma zamanı hatası kaçınmak için ihtiyacınız olan bilgileri kapalı maskeleyebilirsiniz **/RTC** `c`. Örneğin:

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

**s**<br/>
Etkinleştirir çerçevesi çalışma zamanı hata, şu şekilde denetlemesi sırasında yığın:

- Sıfır olmayan bir değer yerel değişkenlere başlatma. Bu, hata ayıklama modunda çalışırken görünmez hataların belirlenmesine yardımcı olur. Yığın değişkenleri sıfır yayın derlemesi için derleme yığın değişkenlerin derleyici iyileştirmeleri nedeniyle karşılaştırıldığında hata ayıklama derlemesinde hala olacak büyük bir olasılık yoktur. Bir program yığınını bir bölümünü kullanmıştır sonra derleyici tarafından hiçbir zaman 0 olarak sıfırlanır. Bu nedenle, aynı yığın alanı kullanmak için sonraki, başlatılmamış yığın değişkenleri önceki Bu yığın bellek kullanımından kaynaklanan kalan değerleri döndürebilir.

- Taşmalarını ve diziler gibi yerel değişkenlerin underruns algılanması. **/ RTC** `s` taşmaları derleyici doldurma bir yapı içinde oluşur bellek erişirken algılamaz. Doldurma kullanarak olabilir [hizalama](../../cpp/align-cpp.md), [/Zp (yapı üyesi hizalama)](zp-struct-member-alignment.md), veya [paketi](../../preprocessor/pack.md), veya yapı öğeleri doldurma eklemek için derleyicinin gerektiren için farklı şekilde sıralayabilir.

- Yığın işaretçisi bozukluğunu algılar yığın işaretçisi doğrulama. Bir çağırma kuralı uyumsuzluğundan yığın işaretçisi bozulmasına neden olabilir. Örneğin, bir işlev işaretçisi kullanılarak, bir işlev olarak verilen bir DLL'de çağırmanızı [__stdcall](../../cpp/stdcall.md) işlevi işaretçisi tanımlayamazsınız ancak [__cdecl](../../cpp/cdecl.md).

**u**<br/>
Bir değişken başlatılmadan kullanıldığında raporlar. Örneğin, oluşturur bir yönerge `C4701` altında bir çalışma zamanı hatası de oluşturabilir **/RTC**`u`. Oluşturan herhangi bir yönerge [Derleyici Uyarısı (düzey 1 ve düzey 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) altında bir çalışma zamanı hatası oluşturur **/RTC**`u`.

Ancak, aşağıdaki kod parçasını göz önünde bulundurun:

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

Değişken başlatılmamış, bu çalışma zamanında raporlanmayacaktır **/RTC**`u`. Örneğin, bir değişken bir işaretçi aracılığıyla başka isim verilir sonra derleyici değil değişkeni izlemek ve rapor başlatılmamış. Aslında, adresini yararlanarak bir değişken başlatabilirsiniz. & Bu durumda bir atama işleci gibi işleci çalışır.

## <a name="remarks"></a>Açıklamalar

Çalışma zamanı hata denetimleri çalışan kodunuzdaki sorunları kolay bir yoludur; Daha fazla bilgi için [nasıl yapılır: Yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks).

Programınızın herhangi birini kullanarak komut satırında derleme yaparsanız **/RTC** derleyici seçenekleri, herhangi bir pragma [en iyi duruma getirme](../../preprocessor/optimize.md) kodunuzda yönergeleri sessizce başarısız olur. Çalışma zamanı hata denetimleri (en iyi duruma getirilmiş) yayın yapılandırması geçerli olmayan olmasıdır.

Kullanmanız gereken **/RTC** geliştirme derlemeler için; **/RTC** perakende derleme için kullanılmamalıdır. **/ RTC** derleyici iyileştirmeleri ile birlikte kullanılamaz ([/O seçenekler (kodu İyileştir)](o-options-optimize-code.md)). Bir program görüntüsü ile oluşturulmuş **/RTC** biraz daha büyük ve ile oluşturulmuş bir görüntüden biraz daha yavaş olacaktır **/Od** (yüzde 5 daha yavaş bir **/Od** oluşturun).

__Msvc_runtıme_checks önişlemci yönergesi kullandığınızda tanımlanır **/RTC** seçeneği veya [/GZ](gz-enable-stack-frame-run-time-error-checking.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **kod oluşturma** özellik sayfası.

1. Birini veya ikisini de aşağıdaki özellikleri değiştirin: **Temel çalışma zamanı denetimleri** veya **daha küçük, onay türü**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[Nasıl yapılır: Yerel Çalışma Zamanı Denetimlerini Kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks)
