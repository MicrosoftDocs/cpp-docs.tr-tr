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
ms.openlocfilehash: 49f0e4bace5f3dd199b58854e838204bd2cd5f3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222023"
---
# <a name="rtc-run-time-error-checks"></a>/RTC (Çalışma Zamanı Hata Denetimleri)

Çalışma zamanı hata denetimleri özelliğini [runtime_checks](../../preprocessor/runtime-checks.md) pragma ile birlikte etkinleştirmek ve devre dışı bırakmak için kullanılır.

## <a name="syntax"></a>Söz dizimi

```
/RTC1
/RTCc
/RTCs
/RTCu
```

## <a name="arguments"></a>Bağımsız değişkenler

**1**<br/>
**/RTC**'nin eşdeğeri `su` .

**,**<br/>
Değer, daha küçük bir veri türüne atandığında ve veri kaybına neden olduğunda bildirir. Örneğin, türünün bir değeri `short 0x101` türünde bir değişkene atanırsa **`char`** .

Bu seçenek, örneğin ilk sekiz bitin bir olarak döndürüldüğünü istiyorsanız, kesmek istediğiniz durumları bildirir **`int`** **`char`** . **/RTC** `c` Atama sonucu olarak herhangi bir bilgi kaybedilmişse,/RTC bir çalışma zamanı hatasına neden olduğundan, **/RTC**'nin sonucu olarak bir çalışma zamanı hatasından kaçınmak için ihtiyacınız olan bilgileri maskeleyebilirsiniz `c` . Örneğin:

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

**malar**<br/>
Yığın çerçevesi çalışma zamanı hata denetimini aşağıdaki gibi sunar:

- Yerel değişkenlerin sıfır dışında bir değere başlatılması. Bu, hata ayıklama modunda çalışırken görünmeyen hataların belirlenmesine yardımcı olur. Bir yayın derlemesi içindeki yığın değişkenlerinin derleyici iyileştirmeleri nedeniyle, yığın değişkenlerinin bir yayın derlemesi ile karşılaştırıldığında bir hata ayıklama derlemesinde sıfır olmaya devam etmesi daha büyük bir şansınız vardır. Bir program yığının bir alanını kullandıktan sonra, derleyici tarafından hiçbir şekilde 0 ' a sıfırlanmaz. Bu nedenle, daha sonra, aynı yığın alanını kullanmak için gerçekleşen başlatılmamış yığın değişkenleri, bu yığın belleğinin önceki kullanımdan itibaren kalan değerleri döndürebilir.

- Yer aşımları ve diziler gibi yerel değişkenlerin yetersiz çalıştırmaları tespit etme. **/RTC** `s` , bir yapı içinde derleyicinin doldurmasını elde eden belleğe erişirken taşmalarını algılamaz. Padding, [/Zp (struct üye hizalaması)](zp-struct-member-alignment.md)veya [Pack](../../preprocessor/pack.md)kullanılarak veya yapı öğelerini derleyicinin doldurma eklemesini gerektirecek şekilde sıraladıysanız [, doldurma](../../cpp/align-cpp.md)gerçekleşebilir.

- Yığın işaretçisi doğrulamasını algılayan yığın işaretçisi doğrulaması. Yığın işaretçisi bozulması, çağırma kuralı uyumsuzluğu nedeniyle oluşabilir. Örneğin, bir işlev işaretçisi kullanarak, bir DLL 'de [__stdcall](../../cpp/stdcall.md) olarak dışarıya aktarılmış bir işlev çağırır ancak işaretçiyi [__cdecl](../../cpp/cdecl.md)işlevi olarak bildirirsiniz.

**larınız**<br/>
Bir değişken başlatılmadan kullanıldığında raporlar. Örneğin, üreten bir yönerge `C4701` **/RTC**altında de bir çalışma zamanı hatası oluşturabilir `u` . [Derleyici Uyarısı (düzey 1 ve düzey 4)](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) üreten herhangi bir yönerge, **/RTC**altında bir çalışma zamanı hatası oluşturur `u` .

Ancak, aşağıdaki kod parçasını göz önünde bulundurun:

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

Bir değişken başlatılmışsa, çalışma zamanında **/RTC**tarafından bildirilmeyecektir `u` . Örneğin, bir değişken bir işaretçi aracılığıyla diğer ad olduktan sonra, derleyici değişkeni izlemez ve başlatılmamış kullanımları rapor etmez. Aslında bir değişkeni adresini alarak başlatabilirsiniz. & işleci bu durumda bir atama işleci gibi çalışmaktadır.

## <a name="remarks"></a>Açıklamalar

Çalışma zamanı hata denetimleri, çalışan kodunuzda sorunları bulmanın bir yoludur; daha fazla bilgi için bkz. [nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks).

Komut satırında **/RTC** derleyici seçeneklerinden herhangi birini kullanarak programınızı derlerseniz, kodunuzdaki tüm pragma [iyileştirme](../../preprocessor/optimize.md) yönergeleri sessizce başarısız olur. Bunun nedeni, sürüm (iyileştirilmiş) derlemesinde çalışma zamanı hata denetimleri geçerli değildir.

Geliştirme yapıları için **/RTC** kullanmanız gerekir; Bir perakende derlemesi için **/RTC** kullanılmamalıdır. **/RTC** derleyici iyileştirmeleri ile kullanılamaz ([/O Seçenekler (kodu en iyi duruma getirme)](o-options-optimize-code.md)). **/RTC** ile derlenen bir program görüntüsü, **/od** ile oluşturulmuş bir görüntüden biraz daha büyük ve biraz daha yavaş olacaktır (bir **/od** derlemeden daha yavaş yüzde 5 ' e kadar).

Herhangi bir **/RTC** seçeneğini veya [/gz](gz-enable-stack-frame-run-time-error-checking.md)kullandığınızda __MSVC_RUNTIME_CHECKS Önişlemci yönergesi tanımlanacak.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Kod oluşturma** Özellik sayfasına tıklayın.

1. Aşağıdaki özelliklerden birini veya her ikisini birden değiştirin: **temel çalışma zamanı denetimleri** veya **daha küçük tür denetimi**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> . ve Özellikler.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[Nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks)
