---
title: Bağlayıcı Araçları Hatası LNK2038
ms.date: 12/15/2017
f1_keywords:
- LNK2038
helpviewer_keywords:
- LNK2038
ms.openlocfilehash: 45078d8e1bdbeb23dd311d915ba2cf47e42b2663
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194518"
---
# <a name="linker-tools-error-lnk2038"></a>Bağlayıcı Araçları Hatası LNK2038

> '*Name*' için uyuşmazlık algılandı: '*value_1*' değeri *filename. obj* içindeki '*value_2*' değeri ile eşleşmiyor

Bağlayıcı tarafından bir sembol uyumsuzluğu algılandı. Bu hata, bir uygulamanın kitaplık veya diğer nesne kodu gibi uygulamanın bağlandığı farklı bölümlerinin sembolün çakışan tanımlarını kullanacağını gösterir. [Algılamamayı Algıla](../../preprocessor/detect-mismatch.md) pragma, bu tür sembolleri tanımlamak ve çakışan değerleri algılamak için kullanılır.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Bu hata, projenizdeki bir nesne dosyası güncel olmadığında ortaya çıkabilir. Bu hatayla ilgili diğer çözümleri denemeden önce, nesne dosyalarının güncel olduğundan emin olmak için temiz bir derleme gerçekleştirin.

Visual Studio, uyumsuz kodun bağlanmasını engellemek için aşağıdaki sembolleri tanımlar, bu da çalışma zamanı hatalarına veya diğer beklenmeyen davranışlara neden olabilir.

- `_MSC_VER`, bir uygulama veya kitaplık oluşturmak için kullanılan Microsoft C++ derleyicisi 'NıN (MSVC) büyük ve küçük sürüm numaralarını gösterir. Bir MSVC sürümü kullanılarak derlenen kod, birincil ve ikincil sürüm numaraları farklı olan bir sürüm kullanılarak derlenen kodla uyumsuzdur. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md)`_MSC_VER`.

   Kullanmakta olduğunuz MSVC sürümüyle uyumlu olmayan bir kitaplığa bağlanıyorsanız ve kitaplığın uyumlu bir sürümünü edinemez ve oluşturamazsınız, projenizi oluşturmak için derleyicinin önceki bir sürümünü kullanabilirsiniz: projenin **platform araç takımı** özelliğini önceki araç takımı olarak değiştirin. Daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- `_ITERATOR_DEBUG_LEVEL`, C++ standart kitaplıkta etkinleştirilen güvenlik ve hata ayıklama özelliklerinin düzeyini gösterir. Bu özellikler, belirli C++ standart kitaplık nesnelerinin gösterimini değiştirebilir ve bu sayede farklı güvenlik ve hata ayıklama özellikleri kullanan bunlarla uyumsuz hale getirir. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md).

- `RuntimeLibrary`, bir uygulama veya kitaplık C++ tarafından kullanılan standart kitaplığın ve C çalışma zamanının sürümünü gösterir. C++ Standart kitaplığın veya C çalışma zamanının bir sürümünü kullanan kod, farklı bir sürüm kullanan kodla uyumsuzdur. Daha fazla bilgi için bkz. [/MD,/MT,/LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md).

- `_PPLTASKS_WITH_WINRT`, [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) kullanan kodun [/ZW](../../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği için farklı bir ayar kullanılarak derlenen nesnelerle bağlantılı olduğunu gösterir. ( **/ZW** , C++/cxdestekler.) PPL kullanan veya bu uygulamaya bağımlı olan kodun, uygulamanın geri kalanında kullanılan **/ZW** ayarı kullanılarak derlenmesi gerekir.

Bu sembollerin değerlerinin Visual Studio çözümünüzdeki projeler genelinde tutarlı olduğundan ve ayrıca uygulamanızın bağlantı kurdukları kod ve kitaplıklarla tutarlı olduklarından emin olun.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Derlemeniz kapsamında bir üçüncü taraf kitaplığı yapılandırmaya çalışırken bu hatayı görürseniz, kitaplığı yüklemek ve oluşturmak için [Vcpkg](../../vcpkg.md), Visual C++ Package Manager 'ı kullanmayı düşünün. Vcpkg, [üçüncü taraf kitaplıkların](https://github.com/Microsoft/vcpkg/tree/master/ports)büyük ve artan bir listesini destekler ve projenizin bir parçası olarak başarılı derlemeler için gereken tüm yapılandırma özelliklerini ve bağımlılıklarını ayarlar. Daha fazla bilgi için ilgili [görsel C++ blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderisine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
