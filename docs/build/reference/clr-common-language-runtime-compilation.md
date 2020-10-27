---
title: /clr (Ortak dil çalışma zamanı derlemesi)
description: C++/CLı ve C++ kodunu yönetilen kod olarak derlemek için Microsoft C++ derleyici seçeneği/clr ' i kullanın.
ms.date: 10/25/2020
f1_keywords:
- /CLR
- VC.Project.VCNMakeTool.CompileAsManaged
- VC.Project.VCCLCompilerTool.CompileAsManaged
helpviewer_keywords:
- cl.exe compiler, common language runtime option
- -clr compiler option [C++]
- clr compiler option [C++]
- /clr compiler option [C++]
- Managed Extensions for C++, compiling
- common language runtime, /clr compiler option
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
ms.openlocfilehash: b4634b63e58344893d99e2217e57693a2c169f66
ms.sourcegitcommit: faecabcdd12ff53eb79dc0df193fc3567f2f037c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92639100"
---
# <a name="clr-common-language-runtime-compilation"></a>`/clr` (Ortak dil çalışma zamanı derlemesi)

Uygulamaların ve bileşenlerin ortak dil çalışma zamanı (CLR) özelliklerini kullanmasına olanak sağlar.

## <a name="syntax"></a>Syntax

> **`/clr`**\[**`:`**_Seçenekler_ ]

## <a name="arguments"></a>Arguments

*Seçenekler*\
Aşağıdaki virgülle ayrılmış bağımsız değişkenlerden biri veya daha fazlası.

- yok

   Seçenek olmadan, **`/clr`** uygulama için meta veriler oluşturur. Meta veriler diğer CLR uygulamaları tarafından tüketilebilir ve uygulamanın diğer CLR bileşenlerinin meta verilerindeki türleri ve verileri kullanmasına olanak sağlar. Daha fazla bilgi için bkz. [karma (yerel ve yönetilen) derlemeler](../../dotnet/mixed-native-and-managed-assemblies.md).

- **`pure`**

   **`/clr:pure` kullanım dışıdır** . Bu seçenek, Visual Studio 2017 ve üzeri sürümlerde kaldırılır. C# ' ye saf MSIL olması gereken bağlantı noktası kodu kullanmanızı öneririz.

- **`safe`**

   **`/clr:safe` kullanım dışıdır** . Bu seçenek, Visual Studio 2017 ve üzeri sürümlerde kaldırılır. C# ' ye güvenli MSIL olması gereken bağlantı noktası kodu kullanmanızı öneririz.

- **`noAssembly`**

   **`/clr:noAssembly` kullanım dışıdır** . Bunun yerine [ `/LN` (MSIL Modülü Oluştur)](ln-create-msil-module.md) kullanın.

   Derleyiciye çıkış dosyasına bir derleme bildirimi eklememasını söyler. Varsayılan olarak **`noAssembly`** seçenek geçerli değildir.

   Bildirimde derleme meta verileri olmayan yönetilen bir program *Modül* olarak bilinir. **`noAssembly`** Seçeneği yalnızca bir modül oluşturmak için kullanılabilir. Ve kullanarak derlerseniz [`/c`](c-compile-without-linking.md) **`/clr:noAssembly`** , [`/NOASSEMBLY`](noassembly-create-a-msil-module.md) bir modül oluşturmak için bağlayıcı aşamasında seçeneğini belirleyin.

   Visual Studio 2005 öncesi, **`/clr:noAssembly`** gereklidir **`/LD`** . **`/LD`** , ' i belirttiğinizde, artık ima edilir **`/clr:noAssembly`** .

- **`initialAppDomain`**

   Bir C++/CLı uygulamasının CLR sürüm 1 ' de çalışmasını sağlar.  Kullanılarak derlenen bir uygulama **`initialAppDomain`** , clr 'nin 1. sürümünde desteklenmediğinden, ASP.NET kullanan bir uygulama tarafından kullanılmamalıdır.

- **`nostdlib`**

   Derleyiciye varsayılan dizini yok saymasını söyler *`\clr`* . System.dll gibi, DLL 'nin birden çok sürümünü dahil ederseniz derleyici hata üretir. Bu seçenek, derleme sırasında kullanmak üzere belirli bir çerçeveyi belirtmenizi sağlar.

## <a name="remarks"></a>Açıklamalar

Yönetilen kod, CLR tarafından incelenelebilecek ve yönetilebilen koddur. Yönetilen kod, yönetilen nesnelere erişebilir. Daha fazla bilgi için bkz. [ `/clr ` kısıtlamalar](clr-restrictions.md).

C++ ' da yönetilen türleri tanımlayan ve tüketen uygulamalar geliştirme hakkında bilgi için bkz. [çalışma zamanı platformları Için bileşen uzantıları](../../extensions/component-extensions-for-runtime-platforms.md).

Kullanılarak derlenen bir uygulama **`/clr`** yönetilen verileri içermeyebilir veya içermeyebilir.

Yönetilen bir uygulamada hata ayıklamayı etkinleştirmek için, bkz. (hata ayıklama [ `/ASSEMBLYDEBUG` Ggableattribute ekleme)](assemblydebug-add-debuggableattribute.md).

Atık toplanan yığında yalnızca CLR türleri oluşturulur. Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md). Yerel koda bir işlev derlemek için `unmanaged` pragma kullanın. Daha fazla bilgi için bkz. [ `managed` , `unmanaged` ](../../preprocessor/managed-unmanaged.md).

Varsayılan olarak **`/clr`** etkin değildir. **`/clr`** Etkin olduğunda **`/MD`** da etkin olur. Daha fazla bilgi için bkz., [ `/MD` `/MT` `/LD` (Run-Time kitaplığı kullanın)](md-mt-ld-use-run-time-library.md). **`/MD`** çalışma zamanı yordamlarının dinamik olarak bağlı, çok iş parçacıklı sürümlerinin standart üstbilgi dosyalarından seçili olmasını sağlar. CLR atık toplayıcısı bir yardımcı iş parçacığında sonlandırıcılar çalıştırdığından yönetilen programlama için çoklu iş parçacığı gereklidir.

Kullanarak derlerseniz **`/c`** , bağlayıcı seçeneğini kullanarak elde edilen çıkış dosyasının clr türünü belirtebilirsiniz [`/CLRIMAGETYPE`](clrimagetype-specify-type-of-clr-image.md) .

**`/clr`****`/EHa`** , **`/EH`** için diğer seçeneklerin destekleneceği anlamına gelir **`/clr`** . Daha fazla bilgi için bkz. [ `/EH` (özel durum işleme modeli)](eh-exception-handling-model.md).

Bir dosyanın CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz [`/CLRHEADER`](clrheader.md) ..

Belirli bir bağlayıcı çağrısına geçirilen tüm modüller aynı çalışma zamanı kitaplığı derleyici seçeneği (veya) kullanılarak derlenmelidir **`/MD`** **`/LD`** .

[`/ASSEMBLYRESOURCE`](assemblyresource-embed-a-managed-resource.md)Bir derlemeye kaynak eklemek için bağlayıcı seçeneğini kullanın. [`/DELAYSIGN`](delaysign-partially-sign-an-assembly.md), [`/KEYCONTAINER`](keycontainer-specify-a-key-container-to-sign-an-assembly.md) , ve [`/KEYFILE`](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bağlayıcı seçenekleri de bir derlemenin oluşturulma şeklini özelleştirmenizi sağlar.

**`/clr`** Kullanıldığında, `_MANAGED` simge 1 olacak şekilde tanımlanır. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Yerel bir nesne dosyasındaki genel değişkenler ilk olarak başlatılır ( `DllMain` yürütülebilir dosya dll ise sırasında) ve ardından yönetilen bölümdeki genel değişkenler başlatılır (herhangi bir yönetilen kod çalıştırılmadan önce). [`#pragma init_seg`](../../preprocessor/init-seg.md) yalnızca yönetilen ve yönetilmeyen kategorilerde başlatma sırasını etkiler.

### <a name="metadata-and-unnamed-classes"></a>Meta veri ve adlandırılmamış sınıflar

Adlandırılmamış sınıflar  `$UnnamedClass$<crc-of-current-file-name>$<index>$` , örneğin, `<index>` derlemede adlandırılmamış sınıfların sıralı bir sayısı olan gibi adlarda meta verilerde görünür. Örneğin, aşağıdaki kod örneği meta verilerde adlandırılmamış bir sınıf oluşturur.

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

Meta verileri görüntülemek için ildasm.exe kullanın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma** açılan listesini **tüm yapılandırmalar** olarak ayarlayın ve **Platform** açılan listesini **tüm platformlar** olarak ayarlayın.

1. **Yapılandırma özellikleri**  >  **Gelişmiş** sayfasını seçin.

1. **Ortak dil çalışma zamanı desteği** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
