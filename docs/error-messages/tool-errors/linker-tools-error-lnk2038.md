---
title: Bağlayıcı Araçları Hatası LNK2038
ms.date: 12/15/2017
f1_keywords:
- LNK2038
helpviewer_keywords:
- LNK2038
ms.openlocfilehash: ea1509d846c0bc5a85f0f0252b611dfd38496bcb
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506005"
---
# <a name="linker-tools-error-lnk2038"></a>Bağlayıcı Araçları Hatası LNK2038

> '*Name*' için uyuşmazlık algılandı: '*value_1*' değeri *filename. obj* içindeki '*value_2*' değeri ile eşleşmiyor

Bağlayıcı tarafından bir sembol uyumsuzluğu algılandı. Bu hata, bir uygulamanın kitaplık veya diğer nesne kodu gibi uygulamanın bağlandığı farklı bölümlerinin sembolün çakışan tanımlarını kullanacağını gösterir. [Algılamamayı Algıla](../../preprocessor/detect-mismatch.md) pragma, bu tür sembolleri tanımlamak ve çakışan değerleri algılamak için kullanılır.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Bu hata, projenizdeki bir nesne dosyası güncel olmadığında ortaya çıkabilir. Bu hatayla ilgili diğer çözümleri denemeden önce, nesne dosyalarının güncel olduğundan emin olmak için temiz bir derleme gerçekleştirin.

Visual Studio, uyumsuz kodun bağlanmasını engellemek için aşağıdaki sembolleri tanımlar, bu da çalışma zamanı hatalarına veya diğer beklenmeyen davranışlara neden olabilir.

- `_MSC_VER` Bir uygulama veya kitaplık oluşturmak için kullanılan Microsoft C++ derleyicisi 'nın (MSVC) büyük ve küçük sürüm numaralarını gösterir. Bir MSVC sürümü kullanılarak derlenen kod, birincil ve ikincil sürüm numaraları farklı olan bir sürüm kullanılarak derlenen kodla uyumsuzdur. Daha fazla bilgi için bkz `_MSC_VER` . [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

   Kullanmakta olduğunuz MSVC sürümüyle uyumlu olmayan bir kitaplığa bağlanıyorsanız ve kitaplığın uyumlu bir sürümünü edinemez ve oluşturamazsınız, projenizi oluşturmak için derleyicinin önceki bir sürümünü kullanabilirsiniz: projenin **platform araç takımı** özelliğini önceki araç takımı olarak değiştirin. Daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- `_ITERATOR_DEBUG_LEVEL` C++ standart kitaplığı 'nda etkinleştirilen güvenlik ve hata ayıklama özelliklerinin düzeyini gösterir. Bu özellikler, belirli C++ standart kitaplık nesnelerinin gösterimini değiştirebilir ve bu sayede farklı güvenlik ve hata ayıklama özellikleri kullanan bunlarla uyumsuz hale getirir. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md).

- `RuntimeLibrary` C++ standart kitaplığı ve bir uygulama veya kitaplık tarafından kullanılan C çalışma zamanının sürümünü gösterir. C++ standart kitaplığı veya C çalışma zamanının bir sürümünü kullanan kod, farklı bir sürüm kullanan kodla uyumsuzdur. Daha fazla bilgi için bkz. [/MD,/MT,/LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md).

- `_PPLTASKS_WITH_WINRT`[Paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) kullanan kodun [/ZW](../../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği için farklı bir ayar kullanılarak derlenen nesnelerle bağlantılı olduğunu gösterir. (**/ZW** C++/cxdestekler.) PPL kullanan veya bu uygulamaya bağımlı olan kodun, uygulamanın geri kalanında kullanılan **/ZW** ayarı kullanılarak derlenmesi gerekir.

Bu sembollerin değerlerinin Visual Studio çözümünüzdeki projeler genelinde tutarlı olduğundan ve ayrıca uygulamanızın bağlantı kurdukları kod ve kitaplıklarla tutarlı olduklarından emin olun.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve vcpkg

Derlemeniz kapsamında bir üçüncü taraf kitaplığı yapılandırmaya çalışırken bu hatayı görürseniz, kitaplığı yüklemek ve derlemek için [vcpkg](../../build/vcpkg.md)'Yi bir C++ paket yöneticisi olarak kullanmayı düşünün. vcpkg, [üçüncü taraf kitaplıkların](https://github.com/Microsoft/vcpkg/tree/master/ports)büyük ve artan bir listesini destekler ve projenizin bir parçası olarak başarılı derlemeler için gereken tüm yapılandırma özelliklerini ve bağımlılıklarını ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları hataları ve uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
