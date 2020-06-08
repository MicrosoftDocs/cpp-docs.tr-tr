---
title: /STD (dil standart sürümünü belirt)
ms.date: 06/04/2020
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: ddb0fc9ad4880ed317a28d7aec5eba1669eabbc5
ms.sourcegitcommit: fe146adb3a02872538637196bb3c45aeeeaaf5c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84507072"
---
# <a name="std-specify-language-standard-version"></a>/STD (dil standart sürümünü belirt)

Desteklenen c++ dil özelliklerini, C++ dil standardının belirtilen sürümünden etkinleştirin.

## <a name="syntax"></a>Sözdizimi

> **`/std:c++14`**\
> **`/std:c++17`**\
> **`/std:c++latest`**]

## <a name="remarks"></a>Açıklamalar

Bu **`/std`** seçenek, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Kodunuzun derlenmesi sırasında etkin olan sürüme özgü ISO C++ programlama dili standart özelliklerini denetlemek için kullanılır. Bu seçenek, belirli yeni dil ve kitaplık özellikleri için desteği devre dışı bırakmanıza olanak tanır. Bu, dil standardının belirli bir sürümüne uygun olan kodunuzu bozabilir. Varsayılan olarak, **`/std:c++14`** C++ dil standardının sonraki sürümlerinde bulunan dil ve standart kitaplık özelliklerini devre dışı bırakan belirtilir. **`/std:c++17`** C++ 17 standardına özgü özellikleri ve davranışları etkinleştirmek için kullanın. Geçerli olarak uygulanan derleyicinin ve sonraki taslak standart için önerilen standart kitaplık özelliklerinin açıkça etkinleştirilmesi için kullanın **`/std:c++latest`** . Tüm C++ 20 özellikleri gereklidir **`/std:c++latest`** ; uygulama tamamlandığında, yeni bir **`/std:c++20`** seçenek etkinleştirilir.

Varsayılan **`/std:c++14`** seçenek, MSVC derleyicisi tarafından uygulanan c++ 14 özelliklerinin kümesini sunar. Bu seçenek, dil standardının daha yeni sürümlerinde değiştirilen veya yeni özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakır. MSVC derleyicisinin önceki sürümlerinde zaten uygulanmış olan bazı C++ 17 özelliklerini devre dışı bırakır. Visual Studio 2015 güncelleştirme 2 ' de veya daha önce kullanılabilir olan özelliklere bağımlılıkları zaten almış olan kullanıcılar için önemli değişikliklerden kaçınmak için, bu özellikler seçenek belirtildiğinde etkin kalır **`/std:c++14`** :

- [Braced-init-Lists ile Auto için kurallar](https://wg21.link/n3922)

- [Şablon şablonunda TypeName-parametreler](https://wg21.link/n4051)

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

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++**, **dil**' i seçin.

1. **C++ dil standardı**' nda, açılan menüden desteklemek istediğiniz dil standardını seçin, sonra değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
