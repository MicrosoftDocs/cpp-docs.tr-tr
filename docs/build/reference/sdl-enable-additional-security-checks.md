---
title: /sdl (Ek Güvenlik Denetimlerini Etkinleştir)
ms.date: 11/26/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
ms.openlocfilehash: d5a85f9648ebcc4064146f22cf5da020e06b7ba3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218981"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (Ek Güvenlik Denetimlerini Etkinleştir)

Önerilen güvenlik geliştirme yaşam döngüsü (SDL) denetimlerini ekler. Bu denetimler, hata olarak güvenlikle ilgili ek uyarıları ve ek güvenli kod oluşturma özelliklerini içerir.

## <a name="syntax"></a>Sözdizimi

> **`/sdl`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

**/SDL** , ve geçersiz kılmalar tarafından sunulan temel güvenlik denetimlerinin bir üst kümesini sunar [`/GS`](gs-buffer-security-check.md) **`/GS-`** . Varsayılan olarak **`/sdl`** kapalıdır. **`/sdl-`** ek güvenlik denetimlerini devre dışı bırakır.

## <a name="compile-time-checks"></a>Derleme zamanı denetimleri

**`/sdl`** Bu uyarıları hata olarak izin veriyor:

|/SDL tarafından etkinleştirilen uyarı|Denk komut satırı anahtarı|Açıklama|
|------------------------------|-------------------------------------|-----------------|
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|Bir birli eksi işleci işaretsiz bir türe uygulandı, sonuçta işaretsiz bir sonuç elde edilir.|
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|Negatif bir integral sabiti işaretsiz türe dönüştürüldü, bu, büyük olasılıkla anlamlı bir sonuç oluşmasına neden olur.|
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|`continue` `break` `goto` Bir bloktaki veya anahtar sözcüklerin kullanımı, `__finally` / `finally` olağan dışı Sonlandırma sırasında tanımsız davranışa sahiptir.|
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|Bir değişken başlatma kodu çalıştırılmayacak.|
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|Başlatılmamış bir yerel değişken kullanımı.|
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|Başlatılmayabilecek yerel bir işaretçi değişkeninin kullanımı.|
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|Belirli C çalışma zamanı (CRT) işlevleri kullanıldığında arabellek taşması.|
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Pragma ile işaretlenmiş bir işlevin kullanımı [`deprecated`](../../preprocessor/deprecated-c-cpp.md) .|
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|Olarak işaretlenen bir işlevin kullanımı [`deprecated`](../../cpp/deprecated-cpp.md) .|

## <a name="runtime-checks"></a>Çalışma zamanı denetimleri

**`/sdl`** Etkinleştirildiğinde, derleyici çalışma zamanında bu denetimleri gerçekleştirmek için kod üretir:

- **`/GS`** İle derleme için eşdeğer, çalışma zamanı arabellek taşması algılama özelliğinin katı modunu sağlar `#pragma strict_gs_check(push, on)` .

- Sınırlı işaretçi temizleme işlemini gerçekleştirir. Başvurusu içermeyen ifadelerde ve Kullanıcı tanımlı yok edicisi olmayan türlerde, bir çağrısından sonra işaretçi başvuruları geçerli olmayan bir adrese ayarlanır **`delete`** . Bu, eski işaretçi başvurularının yeniden kullanılmasını önlemeye yardımcı olur.

- Sınıf üye işaretçisi başlatmayı gerçekleştirir. İşaretçi türünün sınıf üyelerini **`nullptr`** nesne örneklemesinde (Oluşturucu çalışmadan önce) otomatik olarak başlatır. Bu, oluşturucunun açıkça başlamadığı başlatılmamış işaretçiler kullanımını önlemeye yardımcı olur. Derleyicinin ürettiği üye işaretçisi başlatması şu kadar süre çağrılır:

  - Nesne özel (Kullanıcı tanımlı) kullanılarak ayrılmamış`operator new`

  - Nesne bir dizinin parçası olarak ayrılmaz (örneğin `new A[x]` )

  - Sınıf yönetilmiyor veya içeri aktarılmamış

  - Sınıfta Kullanıcı tanımlı bir varsayılan oluşturucu vardır.

  Derleyici tarafından oluşturulan sınıf başlatma işlevi tarafından başlatılacak şekilde, bir üye bir özellik veya sabit değer değil, bir işaretçi olmalıdır.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [Uyarılar,/SDL ve başlatılmamış değişken algılamayı geliştirme](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/).

#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Genel** sayfasında, **SDL denetimleri** açılır listesinden seçeneği belirleyin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
