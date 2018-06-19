---
title: Bağlayıcı araçları hatası LNK2038 | Microsoft Docs
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2038
dev_langs:
- C++
helpviewer_keywords:
- LNK2038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f97f65bbe31e51e5083b34949b47a6963696ee37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301674"
---
# <a name="linker-tools-error-lnk2038"></a>Bağlayıcı Araçları Hatası LNK2038

> uyumsuzluğu algıladı '*adı*': değer '*value_1*'değeri eşleşmeyen'*value_2*' ın *filename.obj*

Bağlayıcı tarafından bir simge uyuşmazlığı algılandı. Bu hata, farklı kısımlarını kitaplıkları veya başka bir nesne gibi bir uygulama, uygulama bağlantılarını simgenin çakışan tanımları kullanma kodu gösterir. [Uyuşmazlığı algılamak](../../preprocessor/detect-mismatch.md) pragma çakışan değerlerine algılamak ve bu tür simgeleri tanımlamak için kullanılır.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Projenizdeki bir nesne dosyası güncel olduğunda bu hata oluşabilir. Bu hata için diğer çözümleri denemeden önce nesne dosyaları geçerli olduğundan emin olmak için temiz bir yapı gerçekleştirin.

Visual Studio çalışma zamanı hataları veya diğer beklenmeyen davranışlara neden olabilir. uyumsuz kod bağlama önlemek için aşağıdaki simgelerden tanımlar.

- `_MSC_VER`  
   Bir uygulama ya da kitaplığı oluşturmak için kullanılan Visual C++ Derleyici birincil ve ikincil sürüm numaralarını gösterir. Visual C++ derleyicisi bir sürümünü kullanarak derlenmiş kod farklı birincil ve ikincil sürüm numarası olan bir sürümünü kullanarak derlenmiş kod ile uyumlu değil. Daha fazla bilgi için bkz: `_MSC_VER` içinde [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

   Kullanmakta olduğunuz ve alma veya kitaplık uyumlu bir sürümü yapı Visual C++ Derleyici sürümü ile uyumlu olmayan bir kitaplığına bağlanıyorsanız, projenizi derleme için derleyici önceki bir sürümünü kullanabilirsiniz: değiştirmek<C1/>Platform araç takımı** önceki araç takımı projeye özelliği. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).

- `_ITERATOR_DEBUG_LEVEL`  
   Güvenlik ve hata ayıklama C++ Standart Kitaplığı'nda etkin özellikleri düzeyini gösterir. Bu özellikler belirli C++ Standart Kitaplığı nesneleri gösterimini değiştirin ve böylece onları olanlar uyumlu bu kullanım farklı güvenlik ve hata ayıklama özellikleri yapın. Daha fazla bilgi için bkz: [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md).

- `RuntimeLibrary`  
   Bir uygulama veya kitaplığı tarafından kullanılan C++ Standart Kitaplığı ve C çalışma zamanı sürümü gösterir. C++ Standart kitaplığı veya C çalışma zamanı bir sürümünü kullanan kodu farklı bir sürümünü kullanan kodu ile uyumlu değil. Daha fazla bilgi için bkz: [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md).

- `_PPLTASKS_WITH_WINRT`  
   Kullanan kodu gösterir [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) için farklı bir ayar kullanarak derlenmiş nesnelere bağlı [/ZW](../../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği. (**/ZW** destekleyen C + +/ CX.) PPL'de üzerinde bağlıdır veya kullanan kodu aynı kullanarak derlenmelidir **/ZW** uygulama geri kalanı kullanılan ayar.

Bu simgeleri değerlerini projeleri tutarlı olduğundan emin olun, Visual Studio çözümünüz ve bu da bunlar uygulamanızı bağlandığı kodu ve kitaplıkları ile tutarlı.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Bir üçüncü taraf kitaplık yapınızın bir parçası yapılandırmak çalışırken bu hatayı görürseniz, kullanmayı [Vcpkg](../../vcpkg.md), Visual C++ paket yüklemek ve kitaplık yapı yöneticisi,. Büyük ve artan Vcpkg desteklemektedir [üçüncü taraf kitaplıkların bir listesi](https://github.com/Microsoft/vcpkg/tree/master/ports)ve tüm başarılı derlemeler için projenizin bir parçası olarak gerekli bağımlılıkları ve yapılandırma özelliklerini ayarlar. Daha fazla bilgi için ilgili bkz [Visual C++ Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderin.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)