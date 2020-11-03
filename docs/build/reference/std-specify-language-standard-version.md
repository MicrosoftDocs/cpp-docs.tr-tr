---
title: /STD (dil standart sürümünü belirt)
description: MSVC derleyici seçeneği/STD, derleyici tarafından desteklenen C veya C++ dil standardını belirler.
ms.date: 10/29/2020
f1_keywords:
- /std
- -std
- /std:c++14
- /std:c++17
- /std:c11
- /std:c17
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 208789071ff028107d3c7311c3b5c6cf3eea7c1d
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238479"
---
# <a name="std-specify-language-standard-version"></a>`/std` (Dil standart sürümünü belirt)

Desteklenen C ve C++ dil özelliklerini, C veya C++ dil standardının belirtilen sürümünden etkinleştirin.

## <a name="syntax"></a>Syntax

> **`/std:c++14`**\
> **`/std:c++17`**\
> **`/std:c++latest`**\
> **`/std:c11`**\
> **`/std:c17`**

## <a name="remarks"></a>Açıklamalar

Bu **`/std`** seçenek, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Bu, kodunuzun derlenmesi sırasında etkin olan sürüme özgü ISO C veya C++ programlama dili standart özelliklerini denetlemek için kullanılır. Bu seçenek, belirli yeni dil ve kitaplık özellikleri için desteği devre dışı bırakmanıza olanak tanır. Bu, dil standardının belirli bir sürümüne uygun olan kodunuzu bozabilir.

### <a name="c-standards-support"></a>C++ standartları desteği

Varsayılan olarak, **`/std:c++14`** C++ dil standardının sonraki sürümlerinde bulunan dil ve standart kitaplık özelliklerini devre dışı bırakan belirtilir. **`/std:c++17`** C++ 17 standardına özgü özellikleri ve davranışları etkinleştirmek için kullanın. Geçerli olarak uygulanan derleyicinin ve sonraki taslak standart için önerilen standart kitaplık özelliklerinin açıkça etkinleştirilmesi için kullanın **`/std:c++latest`** . Tüm C++ 20 özellikleri gereklidir **`/std:c++latest`** ; uygulama tamamlandığında, yeni bir **`/std:c++20`** seçenek etkinleştirilir.

Varsayılan **`/std:c++14`** seçenek, MSVC derleyicisi tarafından uygulanan c++ 14 özelliklerinin kümesini sunar. Bu seçenek, dil standardının daha yeni sürümlerinde değiştirilen veya yeni özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakır. MSVC derleyicisinin önceki sürümlerinde zaten uygulanmış olan bazı C++ 17 özelliklerini devre dışı bırakır. Visual Studio 2015 güncelleştirme 2 ' de veya daha önce kullanılabilir olan özelliklere bağımlılıkları zaten almış olan kullanıcılar için önemli değişikliklerden kaçınmak için, bu özellikler seçenek belirtildiğinde etkin kalır **`/std:c++14`** :

- [`auto`Braced-init-Lists ile ilgili kurallar](https://wg21.link/n3922)

- [`typename` şablon şablonu ' nda-Parametreler](https://wg21.link/n4051)

- [Trigraf kaldırma](https://wg21.link/n4086)

- [Ad alanları ve Numaralandırıcılar için öznitelikler](https://wg21.link/n4266)

- [U8 karakter sabit değerleri](https://wg21.link/n4267)

Belirttiğinizde C++ 14 ve C++ 17 özelliklerinin etkin olduğu bir liste **`/std:c++14`** . Daha fazla bilgi için bkz. [Microsoft C++ dil uyumluluğu tablosundaki](../../overview/visual-cpp-language-conformance.md)notlar.

**`/std:c++17`** Seçeneği, MSVC derleyicisi tarafından uygulanan c++ 17 özelliklerinin tam kümesini sunar. Bu seçenek, C++ 17 ' den sonra yeni veya değiştirilmiş özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakır. Bu, C++ standardının çalışma taslağı ve hata güncelleştirmelerinin sürümlerinde C + + 17 ' den sonraki değişiklikleri içerir.

**`/std:c++latest`** Seçeneği, derleyicide ve kitaplıklarında Şu anda uygulanan C sonrası + + 17 dil ve kitaplık özelliklerini etkin şekilde sunar. Bu özellikler, C++ 20 çalışma taslağındaki değişiklikleri, C++ 17 ' de bulunmayan hata güncelleştirmelerini ve taslak standardı için deneysel teklifleri içerebilir. Desteklenen dil ve kitaplık özelliklerinin bir listesi için bkz. yenilikler [nelerdir Visual C++](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md). Bu **`/std:c++latest`** seçenek, anahtar tarafından korunan özellikleri etkinleştirmeyin **`/experimental`** , ancak bunları etkinleştirmek için gerekli olabilir.

> [!IMPORTANT]
> Tarafından etkinleştirilen derleyici ve kitaplık özellikleri **`/std:c++latest`** , gelecekteki c++ standardında görünebilen özellikleri, Ayrıca, onaylanan c++ 20 özelliklerini temsil eder. Onaylanmamış özellikler, hiçbir bildirimde bulunulmadan son değişikliklere veya kaldırılmasına tabidir.

**`/std`** C++ derlemesi sırasında etkin olan seçenek [ \_ MSVC \_ lang](../../preprocessor/predefined-macros.md) önişlemci makrosu kullanılarak algılanabilir. Daha fazla bilgi için bkz. [Önişlemci makroları](../../preprocessor/predefined-macros.md).

**`/std:c++14`** Ve **`/std:c++latest`** seçenekleri Visual Studio 2015 güncelleştirme 3 ' ten başlayarak kullanılabilir. Bu **`/std:c++17`** seçenek, Visual Studio 2017 sürüm 15,3 ' den başlayarak kullanılabilir. Yukarıda belirtildiği gibi, bazı C++ 17 standart davranışları seçeneği tarafından etkinleştirilir **`/std:c++14`** , ancak diğer tüm c++ 17 özellikleri tarafından etkinleştirilir **`/std:c++17`** . C++ 20 özellikleri **`/std:c++latest`** , uygulama tamamlanana kadar etkinleştirilir.

> [!NOTE]
> MSVC derleyicisi sürümüne veya güncelleştirme düzeyine bağlı olarak, seçenekleri belirttiğinizde C++ 17 özellikleri tam olarak uygulanmayabilir veya tam olarak uyumlu olmayabilir **`/std:c++17`** . Yayın sürümüne göre Visual C++ C++ dil uyumsuzluğuna genel bakış için bkz. [Microsoft C++ dil uygunluğu tablosu](../../overview/visual-cpp-language-conformance.md).

### <a name="c-standards-support"></a>C standartları desteği

Varsayılan olarak, kod C olarak derlendiğinde, MSVC derleyicisi belirli bir C standardına uymuyor. Bazıları ISO C99 'nin bir parçası olan birkaç Microsoft uzantısı ile ANSI c89 uygular. Bazı Microsoft uzantıları derleyici seçeneği kullanılarak devre dışı bırakılabilir [`/Za`](za-ze-disable-language-extensions.md) , ancak diğerleri etkin kalır. Katı c89 uygunluk belirtmek mümkün değildir.

Visual Studio 2019 sürüm 16,8 ' den başlayarak, **`/std:c11`** **`/std:c17`** C olarak derlenen kod belirtebilirsiniz. Bu seçenekler ISO C11 ve ISO C17 'ye karşılık gelen uygunluk modlarını belirtir. Bu standartları desteklemek için yeni Önişlemci gerekli olduğundan, **`/std:c11`** ve **`/std:c17`** derleyici seçenekleri [`/Zc:preprocessor`](zc-preprocessor.md) seçeneği otomatik olarak ayarlar. C11 veya C17 için geleneksel (eski) ön işlemci kullanmak istiyorsanız, **`/Zc:preprocessor-`** derleyici seçeneğini açıkça ayarlamanız gerekir. Seçeneğin ayarlanması **`/Zc:preprocessor-`** beklenmeyen davranışlara neden olabilir ve önerilmez.

> [!NOTE]
> Yayın sırasında, en son Windows SDK ve UCRT kitaplıkları henüz C11 ve C17 kodunu desteklemez. Windows SDK ve UCRT 'nin yayın öncesi sürümü gerekir. Daha fazla bilgi ve yükleme yönergeleri için bkz. [Visual Studio 'Da C11 ve C17 desteğini yükleme](../../overview/install-c17-support.md).

**`/std:c11`** Veya belirttiğinizde **`/std:c17`** MSVC, C11 ve C17 'in gerekli tüm özelliklerini destekler. Derleyici seçenekleri bu işlevler için desteği etkinleştirir:

- [`_Pragma`](../../preprocessor/pragma-directives-and-the-pragma-keyword.md#the-_pragma-preprocessing-operator-c99-c11)

- **`restrict`**

- **`_Noreturn`** ' \<stdnoreturn.h>

- **`_Alignas`****`_Alignof`** ve\<stdalign.h>

- **`_Generic`** ' \<tgmath.h>

- **`_Static_assert`**

IDE, kaynak dosyalarınızda bir *`.c`* dosya uzantısı olduğunda veya derleyici seçeneğini belirttiğinizde IntelliSense ve kod vurgulama Için C ayarlarını kullanır [`/TC`](tc-tp-tc-tp-specify-source-file-type.md) . Şu anda, IntelliSense vurgulama yalnızca standart üstbilgiler tarafından tanıtılan makrolar değil, anahtar sözcükler için kullanılabilir.

C17 büyük ölçüde ISO C11 hata düzeltmesini yayınladığında, C11 için MSVC desteği zaten ilgili tüm hata raporlarını içermektedir. Mevcut olduğunda, makro hariç C11 ve C17 sürümleri arasında fark yoktur `__STDC_VERSION__` . `201112L`C11 için ve C17 için ' i genişletir `201710L` .

Derleyici, ISO C11 'in herhangi bir isteğe bağlı özelliğini desteklemez. Bu isteğe bağlı C11 özelliklerinden bazıları, MSVC mimari nedenlerle uygulanmayan C99 'in gerekli özellikleridir. `__STDC_NO_VLA__`Tek tek özellikler için derleyici desteği düzeylerini algılamak için gibi özellik testi makrolarını kullanabilirsiniz. C-özel önceden tanımlanmış makrolar hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

- Visual Studio 2019 sürüm 16,8 sürümünde uyumlu bir çoklu iş parçacığı, atomik veya karmaşık sayı desteği yoktur.

- `aligned_alloc` Windows yığın uygulama nedeniyle destek eksik. Alternatif olarak kullanılır [`_aligned_malloc`](../../c-runtime-library/reference/aligned-malloc.md) .

- DR 400 desteği şu anda için uygulanmadı `realloc` çünkü bu DEĞIŞIKLIK ABI.

- Değişken uzunluklu dizi (VLA) desteği planlanmıyor. Değişken uzunluklu diziler genellikle karşılaştırılabilir sabit boyutlu dizilerden daha etkilidir. Güvenli ve güvenli bir şekilde uygulandığında eşdeğer yığın belleği ayırmaları ile de verimsiz bir şekilde karşılaştırılır. VLAs `gets()` , kullanım dışı olan ve kaldırma için planlanan saldırı vektörlerini sağlar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** , **C/C++** , **dil** ' i seçin.

1. **C++ dil standardında** (veya c **dilinde standart** ), açılır menüden destekedilecek dil standardını seçin, sonra değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
