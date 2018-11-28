---
title: /sdl (Ek Güvenlik Denetimlerini Etkinleştir)
ms.date: 11/26/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
ms.openlocfilehash: 49ac57f81ef07eb2a9c1e11280e160f0c48fce73
ms.sourcegitcommit: d04dfe95801bafcbd5371e40e626fe5c678343b8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2018
ms.locfileid: "52389948"
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

- Katı modu sağlar **/GS** çalışma zamanı arabellek taşması algılama, ile derleme için eşdeğer `#pragma strict_gs_check(push, on)`.

- Sınırlı işaretçi temizleme gerçekleştirir. Değil içeren ifadeler başvurusunu kaldırır ve hiçbir kullanıcı tanımlı bir yıkıcıya sahip türler, çağrısı yapıldıktan sonra geçerli olmayan bir adrese işaretçi başvuruları ayarlanır `delete`. Yeniden kullanılması engellenen eski işaretçi başvuruları yardımcı olur.

- Sınıf üye işaretçisi başlatma gerçekleştirir. Otomatik olarak başlatır sınıf üyeleri için işaretçi türünün **nullptr** nesne örneklemesini (önce Oluşturucu döngülerinden) üzerinde. Bu oluşturucu açıkça başlatılmaz başlatılmamış işaretçileri kullanımını engeller. Derleyici tarafından oluşturulan üye işaretçisi başlatma adında olduğu sürece:

  - Özel (kullanıcı tanımlı) kullanarak nesne atanmadı `operator new`

  - Nesne, dizi bir parçası olarak atanmamış (örneğin `new A[x]`)

  - Sınıf yönetilen veya içeri aktarılmamış

  - Sınıfın kullanıcı tanımlı varsayılan bir oluşturucu vardır.

  Derleyici tarafından üretilen sınıf başlatma işlevin başlatılması için bir işaretçi ve olmayan bir özellik veya sabit bir üyesi olmalıdır.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [uyarıları, / SDL ve değişken başlatılmamış algılama geliştirme](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/).

#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Üzerinde **genel** sayfasında, ilgili seçeneği seçin **SDL denetimleri** aşağı açılan listesi.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)