---
title: VCBuild ile MSBuild
description: Visual Studio C++ derleme sistemi, visual Studio 2010 ' de VCBuild ile MSBuild 'e değiştirilmiştir.
ms.date: 10/25/2019
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
ms.openlocfilehash: ce3eb9e51a103aa54b74c7b5b4f775eb402269f1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076936"
---
# <a name="vcbuild-vs-msbuild-build-system-changes-in-visual-studio-2010"></a>VCBuild ile MSBuild: Visual Studio 2010 'de sistem değişiklikleri oluşturma

Projeler için C++ MSBuild sistemi, Visual Studio 2010 ' de tanıtılmıştı. Visual Studio 2008 ve önceki sürümlerde VCBuild sistemi kullanılmıştır. VCBuild üzerinde bağımlıya ait olmayan bazı dosya türleri ve kavramlar, MSBuild 'te de farklı şekilde temsil edilir. Bu belgede geçerli derleme sistemindeki farklar açıklanmaktadır. Visual Studio 2008 projesini MSBuild 'e dönüştürmek için Visual Studio 2010 kullanmanız gerekir. Proje dönüştürüldükten sonra, geçerli IDE ve derleyici araç takımını yükseltmek için Visual Studio 'nun en son sürümünü kullanmanız gerekir. Visual Studio 2010 ' i edinme dahil daha fazla bilgi için bkz. [Visual studio 2008 Için yönergeler](use-native-multi-targeting.md#instructions-for-visual-studio-2008).

Aşağıdaki bölümlerde VCBuild 'tan MSBuild 'e yapılan değişiklikler özetlenmektedir. VCBuild projenizin MSBuild tarafından tanınmayan özel yapı kuralları veya makroları varsa, bu yönergeleri MSBuild sistemine nasıl çevirebileceğinizi öğrenmek için bkz. [Visual Studio projeleri C++ ](../build/creating-and-managing-visual-cpp-projects.md) . VCBuild 'ten MSBuild 'e ilk dönüştürme işlemi yalnızca bir ara adımdır. Proje dosyasının tamamen doğru olmaması veya programın hatasız derlenmesi için gerekli değildir. Projeyi Visual Studio 'nun en son sürümünde çalışır durumda olacak şekilde, projeyi MSBuild biçimine dönüştürmek için yalnızca Visual Studio 2010 ' i kullanıyorsunuz.

## <a name="vcproj-is-now-vcxproj"></a>. vcproj şimdi. vcxproj

Proje dosyaları artık. VCPROJ dosya adı uzantısını kullanmaz. Visual Studio 2010, Visual C++ Studio 'nun önceki bir sürümü tarafından oluşturulan proje dosyalarını otomatik olarak, proje dosyaları için. vcxproj uzantısını kullanan MSBuild biçimine dönüştürür.

## <a name="vsprops-is-now-props"></a>. vsprops artık. props

Visual Studio 2008 ve önceki sürümlerde, *Proje özellik sayfası* . vsprops dosya adı uzantısına sahıp olan XML tabanlı bir dosyadır. Proje özellik sayfası, derleyici veya bağlayıcı gibi derleme araçları için anahtarlar belirtmenize ve Kullanıcı tanımlı makrolar oluşturmanıza imkan tanır. MSBuild 'de, proje özellik sayfası için dosya adı uzantısı. props olur.

## <a name="custom-build-rules-and-rules-files"></a>Özel derleme kuralları ve. Rules dosyaları

Visual Studio 2008 ve önceki sürümlerde, *kural dosyası* . Rules dosya adı uzantısına sahıp olan XML tabanlı bir dosyadır. Bir kural dosyası, özel yapı kuralları tanımlamanıza ve bunları bir Visual Studio C++ projesinin yapı işlemine eklemenize olanak tanır. Bir veya daha fazla dosya adı uzantısıyla ilişkilendirilebilen özel bir yapı kuralı, giriş dosyalarını bir veya daha fazla çıktı dosyası oluşturan bir araca geçirmenize olanak sağlar.

MSBuild sisteminde, özel derleme kuralları. Rules dosyası yerine üç dosya türü,. xml,. props ve. targets tarafından temsil edilir. Visual C++ Studio 'nun önceki bir sürümü kullanılarak oluşturulan bir. Rules dosyası visual Studio 2010 ' ye geçirildiğinde, eşdeğer. xml,. props ve. targets dosyaları özgün. Rules dosyası ile birlikte oluşturulup projenizde depolanır.

> [!IMPORTANT]
> Visual Studio 2010 ' de, IDE yeni kuralların oluşturulmasını desteklemez. Bu nedenle, Visual C++ Studio 'nun önceki bir sürümü kullanılarak oluşturulmuş bir projeden bir kural dosyası kullanmanın en kolay yolu projeyi visual Studio 2010 ' e geçirmelidir.

## <a name="inheritance-macros"></a>Devralma makroları

Visual Studio 2008 ve önceki sürümlerde, **$ (Inherit)** makrosu, devralınan özelliklerin proje yapı sistemi tarafından oluşturulan komut satırında görünme sırasını belirtir. **$ (NoInherit)** makrosu, $ (Inherit) örneklerinin yok sayılmasına neden olur ve aksi takdirde devralınabilecek özelliklerin devralınmasına neden olur. Örneğin, varsayılan olarak $ (Inherit) makrosu, [/ı (ek ekleme dizinleri)](../build/reference/i-additional-include-directories.md) derleyici seçeneği kullanılarak belirtilen dosyaların komut satırına eklenmesini sağlar.

Visual Studio 2010 ' de devralma, bir veya daha fazla değişmez değer ve özellik makrosu birleşimi olarak bir özelliğin değeri belirtilerek desteklenir. **$ (Inherit)** ve **$ (NoInherit)** makroları desteklenmez.

Aşağıdaki örnekte, bir özellik sayfasındaki bir özelliğe noktalı virgülle ayrılmış bir liste atanır. Liste, *\<değeri >* sabit değeri ve **$ (** <em>MyProperty</em> **)** makro gösterimi kullanılarak erişilen `MyProperty` özelliğinin değerini içerir.

```
Property=<value>;$(MyProperty)
```

## <a name="vcxprojuser-files"></a>. vcxproj. user dosyaları

Kullanıcı dosyası (. vcxproj. User) kullanıcıya özgü özellikleri, örneğin hata ayıklama ve dağıtım ayarlarını depolar. *Vcxproj. User* dosyası belirli bir kullanıcı için tüm projelere uygulanır.

## <a name="vcxprojfilters-file"></a>. vcxproj. Filters dosyası

Bir projeye dosya eklemek için **Çözüm Gezgini** kullanıldığında, filtreler dosyası ( *. vcxproj. Filters*), dosyanın dosya adı uzantısına bağlı olarak **Çözüm Gezgini** ağaç görünümünde nerede eklendiğini tanımlar.

## <a name="vc-directories-settings"></a>VC + + dizin ayarları

Görsel C++ dizinler ayarları, [VC + + dizinleri Özellik sayfasında](../ide/vcpp-directories-property-page.md)belirtilir. Visual Studio 2008 ve önceki sürümlerde, dizin ayarları Kullanıcı başına uygulanır ve dışlanan dizinlerin listesi, *sysındat* dosyasında belirtilir.

[Devenv/ResetSettings](/visualstudio/ide/reference/resetsettings-devenv-exe) komutunu komut satırında ÇALıŞTıRıRSANıZ, VC + + dizinleri ayarlarını değiştiremezsiniz. Ayrıca, **Araçlar** menüsünü açıp ayarları **Içeri aktar ve dışarı aktar**' a tıklayıp **tüm ayarları Sıfırla** seçeneğini belirlediğinizde ayarları değiştiremezsiniz.

VC + + dizinleri ayarlarını, Visual Studio 'nun önceki bir sürümü tarafından oluşturulan bir *. vssettings* dosyasından geçirmek için:

1. **Araçlar** menüsünü açın, **Içeri ve dışarı aktarma ayarları** ' na tıklayın.
2. **Seçili ortam ayarlarını Içeri aktar** ' ı seçin
3. Sihirbazdaki yönergeleri izleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında MSBuild-C++](../build/msbuild-visual-cpp.md)
