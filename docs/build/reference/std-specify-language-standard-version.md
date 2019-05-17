---
title: / Std (dil standart sürümünü belirt)
ms.date: 05/16/2019
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 0f45727c61d55ff57befc7ff23a3d434e86673bc
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837525"
---
# <a name="std-specify-language-standard-version"></a>/ Std (dil standart sürümünü belirt)

C++ dil standardı'nın belirtilen sürümünden C++ dil özelliklerini etkinleştir desteklenmiyor.

## <a name="syntax"></a>Sözdizimi

> / std:\[c ++ 14\|c ++ 17\|c ++ latest]

## <a name="remarks"></a>Açıklamalar

**/Std** seçenektir ve sonrasında Visual Studio 2017'de kullanılabilir. Sürüme özgü ISO C++ programlama dili standart özelliklerine kodunuzun derleme sırasında etkin denetlemek için kullanılır. Bu seçenek, belirli bir dil sürümüne uyan mevcut kod standart kesme belirli özellikler için destek yeni dil ve kitaplığa devre dışı bırakmanıza olanak tanır. Varsayılan olarak, **/Std: c ++ 14** belirtilirse, hangi devre dışı bırakır dili ve standart kitaplık özellikleri C++ dilinin sonraki sürümlerde, standart bulunamadı. Kullanım **/Std: c ++ 17** C ++ 17 standart özgü özellikler ve davranışı etkinleştirmek için. Şu anda uygulanan derleyici ve standart kitaplık özellikleri ileri taslak standardı için önerilen açıkça etkinleştirmek için **/Std: c ++ Son**. Tüm C ++ 20 özellikleri gerektiren **/std:latest**; uygulama tamamlandığında, yeni bir **/Std: c ++ 20** seçeneği etkinleştirilir.

Varsayılan **/Std: c ++ 14** seçeneği MSVC derleyici tarafından uygulanan C ++ 14 özellikleri kümesini sağlar. Bu seçenek derleyici ve değiştirilen özellikler veya yeni dil standardı, önceki sürümlerinde MSVC derleyicisi, zaten uygulanmış bazı C ++ 17 özellikleri hariç olmak üzere daha yeni sürümlerinde standart kitaplığı desteği devre dışı bırakır. Visual Studio 2015 güncelleştirme 2'den itibaren kullanılabilir özelliklere bağımlılıkları zaten kullanımda kullanıcılar için önemli değişiklikler önlemek için bu özellikleri ne zaman etkin kalmaya devam **/Std: c ++ 14** seçeneği belirtildiğinde:

- [İle küme ayraçlı başlatma listelerinde auto için kuralları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [TypeName şablon şablon parametrelerinde](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Trigrafları kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Ad alanlarında ve numaralandırıcılarda için öznitelikler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Ek bilgi için hangi C ++ 14 ve C ++ 17 özellikleri üzerinde ne zaman etkin **/Std: c ++ 14** olduğundan belirtilen notları bkz [Visual C++ dil uyumluluğu](../../overview/visual-cpp-language-conformance.md).

**/Std: c ++ 17** seçeneği MSVC derleyici tarafından uygulanan C ++ 17 özellikleri kümesini sağlar. Bu seçenek, C ++ 17 sonra derleyici ve değiştirilen özellikler veya yeni sürümlerinde C++ standart çalışma taslak ve hata güncelleştirmeleri standart kitaplığı desteği devre dışı bırakır.

**/Std: c ++ Son** seçeneğini etkinleştirir post-C ++ 17 derleyici ve kitaplıklar şu anda uygulanan dil ve kitaplığa özellikleri. Bunlar, Taslak standardı için Deneysel tekliflerini yanı sıra C ++ 17 bulunmayan C ++ 20 çalışma taslak ve hata güncelleştirmelerin özelliklerini C++ Standart olabilir. Desteklenen Dil ve kitaplık özelliklerinin listesi için bkz: [Visual C++ için Yenilikler](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md). **/Std: c ++ Son** seçeneği tarafından korunan özellikler sağlamaz **/ Deneysel** anahtarı kullanılır, ancak bunları etkinleştirmeniz gerekebilir.

> [!IMPORTANT]
> Derleyici ve kitaplık özellikleri tarafından etkin **/Std: c ++ Son** gelecek sürümlerde görünebilir özelliklerini temsil C++ onaylanmış standart yanı sıra C ++ 20 özellikleri. Henüz onaylanmamış özellikleri değişiklikleri veya temizleme bulunmadan bozucu tabi olan ve bir olarak sağlanan-temelini oluşturur. 

**/Std** seçeneği geçerli bir C++ derleme sırasında kullanarak algılanamıyor [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md) önişlemci makrosu. Daha fazla bilgi için [Önişlemci makroları](../../preprocessor/predefined-macros.md).

**/Std: c ++ 14** ve **/Std: c ++ Son** seçeneklerdir Visual Studio 2015 güncelleştirme 3'te sonraki sürümlerinde kullanılabilir. **/Std: c ++ 17** seçeneği olan Visual Studio 2017 sürüm 15.3 sonraki sürümlerinde kullanılabilir. Bazı C ++ 17 yukarıdaki standart belirtildiği gibi davranışı etkinleştirilir **/Std: c ++ 14** seçeneği yanı sıra, diğer tüm C ++ 17 özellikleri etkindir **/Std: c ++ 17**. C ++ 20 özellikleri etkindir **/std:latest** uygulama tamamlanana kadar.

> [!NOTE]
> MSVC derleyici sürümü veya güncelleştirme düzeyine bağlı olarak, C ++ 17 özellikleri değil tam olarak uygulanabilir veya tam olarak belirttiğiniz zaman uyumlu **/Std: c ++ 17** seçenekleri. C++ dil uyumluluğu Visual C++ sürümü tarafından genel bakış için bkz. [Visual C++ dil uyumluluğu](../../overview/visual-cpp-language-conformance.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++**, **dil**.

1. İçinde **C++ dil standardı**, dil standardı açılır denetimden desteklemek ve ardından seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
