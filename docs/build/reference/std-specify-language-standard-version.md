---
title: -std (dil standart sürümünü belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2017
ms.topic: reference
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
dev_langs:
- C++
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32bbcd47c4ce22882941b6fa9c02373bab32eeb1
ms.sourcegitcommit: 938d118d02543c822a5f58c84d6119d23339e43c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50136000"
---
# <a name="std-specify-language-standard-version"></a>/ Std (dil standart sürümünü belirt)

C++ dil standardı'nın belirtilen sürümünden C++ dil özelliklerini etkinleştir desteklenmiyor.

## <a name="syntax"></a>Sözdizimi

> / Std: [c ++ 14 | c ++ 17 | c ++ latest]

## <a name="remarks"></a>Açıklamalar

**/Std** seçenektir ve sonrasında Visual Studio 2017'de kullanılabilir. Sürüme özgü ISO C++ programlama dili standart özelliklerine kodunuzun derleme sırasında etkin denetlemek için kullanılır. Bu seçenek, belirli bir dil sürümüne uyan mevcut kod standart kesme belirli özellikler için destek yeni dil ve kitaplığa devre dışı bırakmanıza olanak tanır. Varsayılan olarak, **/Std: c ++ 14** belirtilirse, hangi devre dışı bırakır dili ve standart kitaplık özellikleri C++ dilinin sonraki sürümlerde, standart bulunamadı. Kullanım **/Std: c ++ 17** C ++ 17 standart özgü özellikler ve davranışı etkinleştirmek için. En son desteklenen derleyici ve standart kitaplık özellikleri açıkça etkinleştirmek için **/Std: c ++ Son**.

Varsayılan **/Std: c ++ 14** seçeneği, Visual C++ derleyicisi tarafından uygulanan C ++ 14 özellikleri kümesini sağlar. Bu seçenek derleyici ve değiştirilen özellikler veya yeni dil standardı, önceki sürümlerinde Visual C++ derleyicisi, zaten uygulanmış bazı C ++ 17 özellikleri hariç olmak üzere daha yeni sürümlerinde standart kitaplığı desteği devre dışı bırakır. Visual Studio 2015 güncelleştirme 2'den itibaren kullanılabilir özelliklere bağımlılıkları zaten kullanımda kullanıcılar için önemli değişiklikler önlemek için bu özellikleri ne zaman etkin kalmaya devam **/Std: c ++ 14** seçeneği belirtildiğinde:

- [İle küme ayraçlı başlatma listelerinde auto için kuralları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [TypeName şablon şablon parametrelerinde](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Trigrafları kaldırılıyor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Ad alanlarında ve numaralandırıcılarda için öznitelikler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8 karakter değişmez değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

Ek bilgi için hangi C ++ 14 ve C ++ 17 özellikleri üzerinde ne zaman etkin **/Std: c ++ 14** olduğundan belirtilen notları bkz [Visual C++ dil uyumluluğu](../../visual-cpp-language-conformance.md).

**/Std: c ++ 17** seçeneği, Visual C++ derleyicisi tarafından uygulanan C ++ 17 özellikleri kümesini sağlar. Bu seçenek, C ++ 17 sonra derleyici ve değiştirilen özellikler veya yeni sürümlerinde C++ standart çalışma taslak ve hata güncelleştirmeleri standart kitaplığı desteği devre dışı bırakır.

**/Std: c ++ Son** seçenek en çok izlemek için Visual C++ tarafından uygulanan C++ dil ve kitaplığa özellikler kümesi sağlar, ayrıca C ++ 17 bulunmayan C ++ 20 çalışma taslak ve hata güncel C++ standart. Post almak için bu anahtarı kullanın-C ++ 17 dil özellikleri standart kitaplık ve derleyici tarafından desteklenir. Desteklenen Dil ve kitaplık özelliklerinin listesi için bkz: [Visual C++ için Yenilikler](../../what-s-new-for-visual-cpp-in-visual-studio.md). **/Std: c ++ Son** seçeneği tarafından korunan özellikler sağlamaz **/ Deneysel** geçin.

**/Std** seçeneği geçerli bir C++ derleme sırasında kullanarak algılanamıyor [ \_MSVC\_LANG](../../preprocessor/predefined-macros.md) önişlemci makrosu. Daha fazla bilgi için [Önişlemci makroları](../../preprocessor/predefined-macros.md).

**/Std: c ++ 14** ve **/Std: c ++ Son** seçeneklerdir Visual C++ 2015 güncelleştirme 3'te sonraki sürümlerinde kullanılabilir. **/Std: c ++ 17** seçeneği olan Visual C++ 2017 sürüm 15.3 sonraki sürümlerinde kullanılabilir. Bazı C ++ 17 yukarıdaki standart belirtildiği gibi davranışı etkinleştirilir **/Std: c ++ 14** seçeneği yanı sıra, diğer tüm C ++ 17 özellikleri etkindir **/Std: c ++ 17**.

> [!NOTE]
> Visual C++ Derleyici sürümü veya güncelleştirme düzeyine bağlı olarak bazı C ++ 14 veya C ++ 17 özellikleri değil tam olarak uygulanabilir veya tam olarak belirttiğiniz zaman uyumlu **/Std: c ++ 14** veya **/Std: c ++ 17** seçenekleri. Örneğin, Visual C++ 2017 RTM Derleyici tam C ++ 14-uyumlu desteklemez `constexpr`, Aşama 2 adı arama veya ifade SFINAE. C++ dil uyumluluğu Visual C++ sürümü tarafından genel bakış için bkz. [Visual C++ dil uyumluluğu](../../visual-cpp-language-conformance.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++**, **dil**.

1. İçinde **C++ dil standardı**, dil standardı açılır denetimden desteklemek ve ardından seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
