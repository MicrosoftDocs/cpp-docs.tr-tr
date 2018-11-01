---
title: Bağlayıcı Araçları Hatası LNK2038
ms.date: 12/15/2017
f1_keywords:
- LNK2038
helpviewer_keywords:
- LNK2038
ms.openlocfilehash: a22b31f1ac3226271ed7ff03b5be7dad7fff6b93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594317"
---
# <a name="linker-tools-error-lnk2038"></a>Bağlayıcı Araçları Hatası LNK2038

> uyumsuzluğu algılandı için '*adı*': değer '*value_1*'değeri eşleşmiyor'*value_2*' içinde *filename.obj*

Bağlayıcı tarafından bir simge uyumsuzluğu algılandı. Bu hata, kitaplıkları veya diğer nesne dahil olmak üzere, bir uygulamanın farklı bölümleri için uygulama bağlantıları sembolün çakışan tanımlarını kullanmanızı kodu gösterir. [Detect mismatch](../../preprocessor/detect-mismatch.md) pragması, bu tür simgeleri tanımlamak ve bunların çakışan değerlerini algılamak için kullanılır.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Bu hata, projenizde bir nesne dosyası güncel olmadığında oluşabilir. Bu hata için diğer çözümleri denemeden önce nesne dosyalarının güncel olduğundan emin olmak için bir temiz yapı gerçekleştirin.

Visual Studio, çalışma zamanı hataları veya diğer beklenmeyen davranışlara neden olabilir. uyumsuz kod bağlanmasını önlemek için aşağıdaki simgeleri tanımlar.

- `_MSC_VER` Bir uygulama veya kitaplık oluşturmak için kullanılan Visual C++ derleyicisi birincil ve ikincil sürüm numaralarını belirtir. Visual C++ derleyicisinin bir sürümünü kullanarak derlenmiş kod, farklı büyük ve küçük sürüm numaralarına sahip bir sürüm kullanarak derlenmiş kod ile uyumlu değil. Daha fazla bilgi için `_MSC_VER` içinde [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

   Kullanmakta olduğunuz ve alamıyor veya kitaplığın uyumlu bir sürümünü oluşturmak Visual C++ Derleyici sürümü ile uyumlu olmayan bir kitaplığa bağlıyorsanız, projenizi yapılandırmak için derleyicinin önceki bir sürümünü kullanabilirsiniz: değiştirme<C1/>Platform araç takımını** önceki araç takımı proje özelliği. Daha fazla bilgi için [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- `_ITERATOR_DEBUG_LEVEL` Güvenlik ve C++ Standart kitaplığında etkin özelliklerin hata ayıklama düzeyini gösterir. Bu özellikler belirli C++ Standart Kitaplığı nesnelerinin gösterimini değiştirebilir ve böylece onları uyumsuz bu kullanım farklı güvenlik ve hata ayıklama özellikleri yapın. Daha fazla bilgi için [_ıterator_debug_level](../../standard-library/iterator-debug-level.md).

- `RuntimeLibrary` Bir uygulama veya kitaplık tarafından kullanılan C++ Standart Kitaplığı ve C çalışma zamanı sürümünü gösterir. C++ Standart kitaplığı veya C çalışma zamanının bir sürümünü kullanan kodu farklı bir sürüm kullanan kod ile uyumlu değil. Daha fazla bilgi için [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md).

- `_PPLTASKS_WITH_WINRT` Kullanan kodu gösteren [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) için farklı bir ayar kullanılarak derlenmiş nesneleri bağlandığı [/ZW](../../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği. (**/ZW** destekler: C + +/ CX.) PPL üzerinde bağlıdır veya kullanan kodu aynı kullanarak derlenmelidir **/ZW** uygulama geri kalanında kullanılan ayar.

Bu simge değerlerinin projelerle tutarlı olduğundan emin olun, Visual Studio çözümünüzün ve aynı zamanda uygulamanızın bağlı kod ve kitaplıklarla tutarlı oldukları.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Bu hatayı görürseniz, bir üçüncü taraf kitaplığı yapınızın bir parçası olarak yapılandırılmaya çalışılırken kullanmayı [Vcpkg](../../vcpkg.md), Visual C++ paketi yükleyip kitaplığı derleme Yöneticisi. Vcpkg destekleyen çok ve artan [üçüncü taraf kitaplıkların listesini](https://github.com/Microsoft/vcpkg/tree/master/ports)ve tüm başarılı derleme için projenizin bir parçası olarak gerekli bağımlılıkları ve yapılandırma özelliklerini ayarlar. Daha fazla bilgi için bkz. ilgili [Visual C++ blogu](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderin.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)