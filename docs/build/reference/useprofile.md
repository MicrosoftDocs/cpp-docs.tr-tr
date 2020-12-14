---
description: Daha fazla bilgi edinin:/USEPROFıLE (iş parçacığı güvenli modunda PGO Çalıştır)
title: /USEPROFıLE (LTCG ile PGO verileri kullanın)
ms.date: 03/14/2018
f1_keywords:
- USEPROFILE
ms.openlocfilehash: c6c293b8467ea308dc2f7b4a4cd916cc5d9ac4c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247052"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/USEPROFıLE (iş parçacığı güvenli modunda PGO Çalıştır)

Bu bağlayıcı seçeneği [/LTCG ile birlikte (bağlama zamanı kodu oluşturma](ltcg-link-time-code-generation.md) , bağlayıcıya profil temelli iyileştirme (PGO) eğitim verilerini kullanarak derlemeyi söyler.

## <a name="syntax"></a>Syntax

> **/USEPROFILE**[**:**{**agresif** | **PGD =**_filename_}]

### <a name="arguments"></a>Arguments

**SALDıRGAN**<br/>
Bu isteğe bağlı bağımsız değişken, en iyileştirilmiş kod oluşturma sırasında agresif hız iyileştirmelerinin kullanılması gerektiğini belirtir.

**PGD** = *dosya adı*<br/>
. Pgd dosyası için bir taban dosya adı belirtir. Varsayılan olarak, bağlayıcı temel yürütülebilir dosya adını. pgd uzantısıyla kullanır.

## <a name="remarks"></a>Açıklamalar

**/Useprofile** bağlayıcı seçeneği, PGO eğitim verilerine dayalı iyileştirilmiş bir derlemeyi oluşturmak veya güncelleştirmek için **/LTCG** ile birlikte kullanılır. Kullanım dışı bırakılan **/LTCG: PGUPDATE** ve **/LTCG: pgoptimize** seçeneklerinin eşdeğeridir.

İsteğe bağlı **agresif** bağımsız değişken hız için optimize etmeye çalışmak üzere boyutla ilgili buluşsal yöntemleri devre dışı bırakır. Bu, yürütülebilir dosyanızın boyutunu önemli ölçüde artıran ve elde edilen hızı artmayan iyileştirmelere neden olabilir. **Agresif** kullanmamalıdır ve kullanarak sonuçları ve karşılaştırmanız gerekir. Bu bağımsız değişken açıkça belirtilmelidir; Varsayılan olarak etkinleştirilmemiştir.

**PGD** bağımsız değişkeni, [/genprofile veya/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)gibi kullanılacak eğitim verileri. pgd dosyası için isteğe bağlı bir ad belirtir. Kullanım dışı bırakılan **/PGD** anahtarıyla eşdeğerdir. Varsayılan olarak veya *dosya adı* belirtilmemişse, yürütülebilir dosya ile aynı temel adı taşıyan bir. pgd dosyası kullanılır.

**/Useprofile** bağlayıcı seçeneği Visual Studio 2015 ' de yenidir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **iyileştirme** özellik sayfasını seçin.

1. **Bağlama zamanı kodu üretimi** özelliğinde **bağlama zaman kodu oluşturma 'yı (/LTCG) kullanın**.

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna **/useprofile** seçeneğini ve isteğe bağlı bağımsız değişkenleri girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/GENPROFILE ve/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profil temelli Iyileştirmeler](../profile-guided-optimizations.md)<br/>
[Profile-Guided Iyileştirmeleri için ortam değişkenleri](../environment-variables-for-profile-guided-optimizations.md)<br/>
