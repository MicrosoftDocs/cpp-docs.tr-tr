---
title: /STD (dil standart sürümünü belirt)
ms.date: 05/16/2019
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 4583bef3ef3033b6ba493ccac1c4fc5360c70e35
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624886"
---
# <a name="std-specify-language-standard-version"></a>/STD (dil standart sürümünü belirt)

Dil standardının C++ belirtilen sürümünden desteklenen dil özelliklerini etkinleştirin. C++

## <a name="syntax"></a>Sözdizimi

> /std:\[c++ 14\|c++ 17\|c + + en son]

## <a name="remarks"></a>Açıklamalar

**/STD** seçeneği Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Kodunuzun derlenmesi sırasında etkin olan sürüme özgü ISO C++ programlama dili standart özelliklerini denetlemek için kullanılır. Bu seçenek, dil standardının belirli bir sürümüne uygun olan kodunuzu bozabilecek bazı yeni dil ve kitaplık özellikleri için desteği devre dışı bırakmanızı sağlar. Varsayılan olarak, C++ dil standardının sonraki sürümlerinde bulunan dil ve standart kitaplık özelliklerini devre dışı bırakan **/std: c++ 14** belirtilir. C++ 17 standardına özgü özellikleri ve davranışları etkinleştirmek için **/std: c++ 17** kullanın. Geçerli olarak uygulanan derleyicinin ve sonraki taslak standart için önerilen standart kitaplık özelliklerinin açıkça etkinleştirilmesi için **/std: c + + latest**' ı kullanın. Tüm C++ 20 özellikleri **/std: C + + latest**gerektirir; uygulama tamamlandığında, yeni bir **/std: c++ 20** seçeneği etkinleştirilir.

Varsayılan **/std: c++ 14** SEÇENEĞI, MSVC derleyicisi tarafından uygulanan c++ 14 özelliklerinin kümesini sunar. Bu seçenek, dil standardının daha yeni sürümlerinde değiştirilen veya yeni olan özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakarak MSVC derleyicisinin önceki sürümlerinde zaten uygulanmış olan bazı C++ 17 özellikleri hariç kalır. Visual Studio 2015 güncelleştirme 2 itibariyle sunulan özelliklerde bağımlılıkları zaten almış olan kullanıcılar için önemli değişikliklerden kaçınmak için, **/std: c++ 14** seçeneği belirtildiğinde bu özellikler etkin kalır:

- [Braced-init-Lists ile Auto için kurallar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3922.html)

- [Şablon şablonunda TypeName-parametreler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4051.html)

- [Trigraf kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4086.html)

- [Ad alanları ve Numaralandırıcılar için öznitelikler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4266.html)

- [U8 karakter sabit değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4267.html)

**/Std: c++ 14** belirtildiğinde c++ 14 ve c++ 17 özelliklerinin etkinleştirildiği ek bilgiler Için, [Microsoft C++ dil uyumluluğu tablosundaki](../../overview/visual-cpp-language-conformance.md)notlara bakın.

**/Std: c++ 17** SEÇENEĞI, MSVC derleyicisi tarafından uygulanan c++ 17 özelliklerinin tam kümesini sunar. Bu seçenek, C++ 17 ' den sonra C++ standart 'ın çalışma taslağı ve hata güncelleştirmeleri sürümlerinde değiştirilen veya yeni olan özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakır.

**/Std: c + + en son** seçeneği, derleyicide ve kitaplıklarda Şu anda uygulanmış olan post-c + + 17 dil ve kitaplık özelliklerini sunar. Bunlar, c++ 20 çalışma taslağı ve C++ standart hata güncelleştirmelerinden oluşan ve c++ 17 ' de bulunmayan ve taslak standart için deneysel tekliflerin bulunduğu özellikleri içerebilir. Desteklenen dil ve kitaplık özelliklerinin bir listesi için bkz. [ C++Visual için yenilikler ](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md). **/Std: c + + latest** seçeneği, **/deneysel** anahtar tarafından korunan özellikleri etkinleştirmez, ancak bunları etkinleştirmek için gerekli olabilir.

> [!IMPORTANT]
> **/Std: c + + en son** tarafından etkinleştirilen derleyici ve kitaplık özellikleri, gelecekteki C++ bir standart içinde görünebilen özellikleri, Ayrıca, onaylanmış c++ 20 özelliklerini temsil eder. Onaylanmamış özellikler, hiçbir bildirimde bulunulmadan son değişikliklere veya kaldırılmasına tabidir. 

Bir C++ derleme sırasında etkin olan **/std** seçeneği, [\_MSVC\_lang](../../preprocessor/predefined-macros.md) önişlemci makrosu kullanılarak algılanabilir. Daha fazla bilgi için bkz. [Önişlemci makroları](../../preprocessor/predefined-macros.md).

**/Std: c++ 14** ve **/std: c + + en son** seçenekleri Visual Studio 2015 güncelleştirme 3 ' ten başlayarak kullanılabilir. **/Std: c++ 17** seçeneği, Visual Studio 2017 sürüm 15,3 ' den başlayarak kullanılabilir. Yukarıda belirtildiği gibi, bazı C++ 17 standart davranışları **/std: c++ 14** seçeneği tarafından etkinleştirilir, ancak diğer tüm c++ 17 özellikleri **/std: c++ 17**tarafından etkinleştirilir. C++ 20 özellikleri, uygulama tamamlanana kadar **/std: latest** tarafından etkinleştirilir.

> [!NOTE]
> MSVC derleyicisi sürümüne veya güncelleştirme düzeyine bağlı olarak, **/std: c++ 17** seçeneklerini belirttiğinizde, c++ 17 özellikleri tam olarak uygulanmayabilir veya tam olarak uyumlu olmayabilir. Yayın sürümüne göre görselde C++ C++ dil uyumsuzluğuna genel bakış için bkz. [Microsoft C++ dil uygunluk tablosu](../../overview/visual-cpp-language-conformance.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++** , **dil**' i seçin.

1. **C++ Dil standardı**' nda, açılan menüden desteklemek istediğiniz dil standardını seçin, sonra değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
