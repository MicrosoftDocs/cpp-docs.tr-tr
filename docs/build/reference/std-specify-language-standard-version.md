---
title: / Std (dil standart sürümünü belirt)
ms.date: 11/26/2018
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: d66a9ed445e28de2341aa2a07f249c10cba83da4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812011"
---
# <a name="std-specify-language-standard-version"></a>/ Std (dil standart sürümünü belirt)

C++ dil standardı'nın belirtilen sürümünden C++ dil özelliklerini etkinleştir desteklenmiyor.

## <a name="syntax"></a>Sözdizimi

> / std:\[c ++ 14\|c ++ 17\|c ++ latest]

## <a name="remarks"></a>Açıklamalar

**/Std** seçenektir ve sonrasında Visual Studio 2017'de kullanılabilir. Sürüme özgü ISO C++ programlama dili standart özelliklerine kodunuzun derleme sırasında etkin denetlemek için kullanılır. Bu seçenek, belirli bir dil sürümüne uyan mevcut kod standart kesme belirli özellikler için destek yeni dil ve kitaplığa devre dışı bırakmanıza olanak tanır. Varsayılan olarak, **/Std: c ++ 14** belirtilirse, hangi devre dışı bırakır dili ve standart kitaplık özellikleri C++ dilinin sonraki sürümlerde, standart bulunamadı. Kullanım **/Std: c ++ 17** C ++ 17 standart özgü özellikler ve davranışı etkinleştirmek için. Şu anda uygulanan derleyici ve standart kitaplık özellikleri ileri taslak standardı için önerilen açıkça etkinleştirmek için **/Std: c ++ Son**.

Varsayılan **/Std: c ++ 14** seçeneği MSVC derleyici tarafından uygulanan C ++ 14 özellikleri kümesini sağlar. Bu seçenek derleyici ve değiştirilen özellikler veya yeni dil standardı, önceki sürümlerinde MSVC derleyicisi, zaten uygulanmış bazı C ++ 17 özellikleri hariç olmak üzere daha yeni sürümlerinde standart kitaplığı desteği devre dışı bırakır. Visual Studio 2015 güncelleştirme 2'den itibaren kullanılabilir özelliklere bağımlılıkları zaten kullanımda kullanıcılar için önemli değişiklikler önlemek için bu özellikleri ne zaman etkin kalmaya devam **/Std: c ++ 14** seçeneği belirtildiğinde:

- [İle küme ayraçlı başlatma listelerinde auto için kuralları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [TypeName şablon şablon parametrelerinde](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Trigrafları kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Ad alanlarında ve numaralandırıcılarda için öznitelikler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Ek bilgi için hangi C ++ 14 ve C ++ 17 özellikleri üzerinde ne zaman etkin **/Std: c ++ 14** olduğundan belirtilen notları bkz [Visual C++ dil uyumluluğu](../../visual-cpp-language-conformance.md).

**/Std: c ++ 17** seçeneği MSVC derleyici tarafından uygulanan C ++ 17 özellikleri kümesini sağlar. Bu seçenek, C ++ 17 sonra derleyici ve değiştirilen özellikler veya yeni sürümlerinde C++ standart çalışma taslak ve hata güncelleştirmeleri standart kitaplığı desteği devre dışı bırakır.

**/Std: c ++ Son** seçeneğini etkinleştirir post-C ++ 17 derleyici ve kitaplıklar şu anda uygulanan dil ve kitaplığa özellikleri. Bunlar, Taslak standardı için Deneysel tekliflerini yanı sıra C ++ 17 bulunmayan C ++ 20 çalışma taslak ve hata güncelleştirmelerin özelliklerini C++ Standart olabilir. Desteklenen Dil ve kitaplık özelliklerinin listesi için bkz: [Visual C++ için Yenilikler](../../what-s-new-for-visual-cpp-in-visual-studio.md). **/Std: c ++ Son** seçeneği tarafından korunan özellikler sağlamaz **/ Deneysel** anahtarı kullanılır, ancak bunları etkinleştirmeniz gerekebilir.

> [!IMPORTANT]
> Derleyici ve kitaplık özellikleri tarafından etkin **/Std: c ++ Son** olarak sağlanan-olduğu ve desteği olmadan. Değişiklikleri veya temizleme bulunmadan bozucu tabi değildirler. Standart bir sonraki sürümünde görünebilir dil özelliklerinin önizleme olarak yöneliktir, ancak standart bir süreç olduğu. Kullanma **/Std: c ++ 17** son ISO C++ standart özellikleri kullanmak için.

**/Std** seçeneği geçerli bir C++ derleme sırasında kullanarak algılanamıyor [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md) önişlemci makrosu. Daha fazla bilgi için [Önişlemci makroları](../../preprocessor/predefined-macros.md).

**/Std: c ++ 14** ve **/Std: c ++ Son** seçeneklerdir Visual C++ 2015 güncelleştirme 3'te sonraki sürümlerinde kullanılabilir. **/Std: c ++ 17** seçeneği olan Visual C++ 2017 sürüm 15.3 sonraki sürümlerinde kullanılabilir. Bazı C ++ 17 yukarıdaki standart belirtildiği gibi davranışı etkinleştirilir **/Std: c ++ 14** seçeneği yanı sıra, diğer tüm C ++ 17 özellikleri etkindir **/Std: c ++ 17**.

> [!NOTE]
> MSVC derleyici sürümü veya güncelleştirme düzeyine bağlı olarak bazı C ++ 14 veya C ++ 17 özellikleri değil tam olarak uygulanabilir veya tam olarak belirttiğiniz zaman uyumlu **/Std: c ++ 14** veya **/Std: c ++ 17** seçenekleri. Örneğin, Visual C++ 2017 RTM Derleyici tam C ++ 14-uyumlu desteklemez `constexpr`, Aşama 2 adı arama veya ifade SFINAE. C++ dil uyumluluğu Visual C++ sürümü tarafından genel bakış için bkz. [Visual C++ dil uyumluluğu](../../visual-cpp-language-conformance.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++**, **dil**.

1. İçinde **C++ dil standardı**, dil standardı açılır denetimden desteklemek ve ardından seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
