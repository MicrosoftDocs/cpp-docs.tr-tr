---
title: /RTC (Çalışma zamanı hata denetimleri)
description: Çalışma zamanı hata denetimleri için Microsoft C/C++ derleyicisi/RTC seçenekleri.
ms.date: 07/31/2020
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
ms.openlocfilehash: 888a81d0d5c21b0b85420a43d534c5b2742aa082
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765230"
---
# <a name="rtc-run-time-error-checks"></a>`/RTC` (Çalışma zamanı hata denetimleri)

Çalışma zamanı hata denetimleri özelliğini [runtime_checks](../../preprocessor/runtime-checks.md) pragma ile birlikte etkinleştirmek ve devre dışı bırakmak için kullanılır.

## <a name="syntax"></a>Söz dizimi

> **`/RTC1`**\
> **`/RTCc`**\
> **`/RTCs`**\
> **`/RTCu`**

## <a name="arguments"></a>Bağımsız değişkenler

**`/RTC1`**<br/>
İle eşdeğerdir **`/RTCsu`** .

**`/RTCc`**<br/>
Değer, daha küçük bir veri türüne atandığında ve veri kaybına neden olduğunda bildirir. Örneğin, türünde bir **`short`** değişkene atanmış bir tür değeri olup olmadığını bildirir `0x0101` **`char`** .

Bu seçenek, kesilmesini planladığınız durumları rapor edebilir. Örneğin, bir olarak döndürülen ilk 8 bitini istediğiniz zaman **`int`** **`char`** . **`/RTCc`** Bir atama herhangi bir bilgi kaybına neden olursa, çalışma zamanı hatasına neden olur, ancak çalışma zamanı hatasından kaçınmak için ihtiyacınız olan bilgilerin ilk maskesini kaldırın. Örneğin:

```C
#include <crtdbg.h>

char get8bits(unsigned value, int position) {
   _ASSERT(position < 32);
   return (char)(value >> position);
   // Try the following line instead:
   // return (char)((value >> position) & 0xff);
}

int main() {
   get8bits(12341235,3);
}
```

**`/RTCc`**, Standarda uygun kodu reddettiğinden, C++ standart kitaplığı tarafından desteklenmez. **`/RTCc`** Ve C++ standart kitaplığı kullanan kod derleyici hatası [C1189](../../error-messages/compiler-errors-1/fatal-error-c1189.md)neden olabilir. `_ALLOW_RTCc_IN_STL`Uyarıyı sessizlik için tanımlayabilir ve **`/RTCc`** seçeneğini kullanabilirsiniz.

**`/RTCs`**<br/>
Yığın çerçevesi çalışma zamanı hata denetimini aşağıdaki gibi sunar:

- Yerel değişkenlerin sıfır dışında bir değere başlatılması. Bu seçenek, hata ayıklama modunda çalışırken görünmeyen hataların belirlenmesine yardımcı olur. Yığın değişkenlerinin bir yayın derlemesi ile karşılaştırıldığında hata ayıklama derlemesinde sıfır değeri olmaya devam etmesi daha büyük bir şansınız vardır. Bunun nedeni, bir yayın derlemesinde yığın değişkenlerinin derleyici iyileştirmelerinden kaynaklanır. Bir program yığının bir alanını kullandıktan sonra, derleyici tarafından hiçbir şekilde 0 ' a sıfırlanmaz. Diğer bir deyişle, daha sonra aynı yığın alanının kullanıldığı başlatılmamış yığın değişkenleri, bu yığın belleğinin önceki kullanımı üzerinden kalan değerleri döndürebilir.

- Yer aşımları ve diziler gibi yerel değişkenlerin yetersiz çalıştırmaları tespit etme. **`/RTCs`** , bir yapıda derleyicinin doldurmasını elde eden belleğe erişirken taşmaları algılamaz. Doldurma [`align`](../../cpp/align-cpp.md) , [ `/Zp` (struct member hizalaması)](zp-struct-member-alignment.md)veya ya [`pack`](../../preprocessor/pack.md) da yapı öğelerini, derleyicinin doldurma eklemesi için gerekli olacak şekilde sıraladıysanız gerçekleşebilir.

- Yığın işaretçisi doğrulamasını algılayan yığın işaretçisi doğrulaması. Yığın işaretçisi bozulması, çağırma kuralı uyumsuzluğu nedeniyle oluşabilir. Örneğin, bir işlev işaretçisi kullanarak, olarak aktarılmış bir DLL içinde bir işlevi çağırır, [`__stdcall`](../../cpp/stdcall.md) ancak işaretçiyi işlevi olarak bildirirsiniz [`__cdecl`](../../cpp/cdecl.md) .

**`/RTCu`**<br/>
Bir değişken başlatılmadan kullanıldığında raporlar. Örneğin, uyarı C4701 üreten bir yönerge, altında bir çalışma zamanı hatası da oluşturabilir **`/RTCu`** . [Derleyici Uyarısı (düzey 1 ve düzey 4)](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) üreten tüm yönergeler, altında bir çalışma zamanı hatası oluşturur **`/RTCu`** .

Ancak, aşağıdaki kod parçasını göz önünde bulundurun:

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

Bir değişken başlatılmış olabilir, tarafından çalışma zamanında raporlanmaz **`/RTCu`** . Örneğin, bir değişken bir işaretçi üzerinden diğer ad olduktan sonra, derleyici değişkeni izlemez ve başlatılmamış kullanımları rapor etmez. Aslında bir değişkeni adresini alarak başlatabilirsiniz. **`&`** İşleci bu durumda bir atama işleci gibi çalışmaktadır.

## <a name="remarks"></a>Açıklamalar

Çalışma zamanı hata denetimleri, çalışan kodunuzda sorunları bulmanın bir yoludur; daha fazla bilgi için bkz. [nasıl yapılır: yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks).

Komut satırında birden çok seçenek belirtebilirsiniz **`/RTC`** . Seçenek bağımsız değişkenleri birleştirilebilir; Örneğin, **`/RTCcu`** ile aynıdır **`/RTCc /RTCu`** .

Komut satırında herhangi bir derleyici seçeneğini kullanarak programınızı derlerseniz **`/RTC`** , kodunuzda herhangi bir pragma [`optimize`](../../preprocessor/optimize.md) yönergesi sessizce başarısız olur. Bunun nedeni, sürüm (iyileştirilmiş) derlemede çalışma zamanı hata denetimleri geçerli değildir.

**`/RTC`** Geliştirme yapıları için kullanın; **`/RTC`** Yayın derlemesi için kullanmayın. **`/RTC`** Derleyici iyileştirmeleriyle kullanılamaz ([ `/O` Seçenekler (kod iyileştirin)](o-options-optimize-code.md)). İle oluşturulmuş bir program görüntüsü **`/RTC`** , ile oluşturulmuş bir görüntüden biraz daha büyük ve biraz daha yavaştır **`/Od`** (bir derlemeden daha yavaş yüzde 5 ' e kadar **`/Od`** ).

`__MSVC_RUNTIME_CHECKS`Önişlemci yönergesi herhangi bir seçeneği veya herhangi bir seçeneği kullandığınızda tanımlanır **`/RTC`** [`/GZ`](gz-enable-stack-frame-run-time-error-checking.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **kod oluşturma** özellik sayfasını seçin.

1. Aşağıdaki özelliklerden birini veya her ikisini birden değiştirin: **temel çalışma zamanı denetimleri** veya **daha küçük tür denetimi**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> . ve Özellikler.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>
[Nasıl yapılır: Yerel çalışma zamanı denetimlerini kullanma](/visualstudio/debugger/how-to-use-native-run-time-checks)
