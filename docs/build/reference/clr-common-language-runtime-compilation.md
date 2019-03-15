---
title: /clr (Ortak Dil Çalışma Zamanı Derlemesi)
ms.date: 09/18/2018
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
ms.openlocfilehash: 124f54f46e71ac8fb8511d12fba43ab77d04c32e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822475"
---
# <a name="clr-common-language-runtime-compilation"></a>/clr (Ortak Dil Çalışma Zamanı Derlemesi)

Ortak dil çalışma zamanı (CLR) özellikleri kullanmak, uygulamaları ve bileşenleri sağlar.

## <a name="syntax"></a>Sözdizimi

> **/ CLR**[**:**_seçenekleri_]

## <a name="arguments"></a>Arguments

*Seçenekler*<br/>
Bir veya daha fazla aşağıdaki anahtarları, virgülle ayrılmış.

- yok

   Hiçbir seçenek olmadan **/CLR** uygulama meta verilerini oluşturur. Meta veriler, diğer CLR uygulamaları tarafından tüketilebilecek ve türleri ve diğer CLR bileşenlerine ait meta verilerdeki veri kullanmak uygulamayı etkinleştirir. Daha fazla bilgi için [karışık (yerel ve yönetilen) derlemeler](../../dotnet/mixed-native-and-managed-assemblies.md).

- **saf**

   **/ CLR: pure kullanım dışı**. Seçeneği, Visual Studio 2017'de kaldırılır. Saf MSIL C# için gereken kod bağlantı noktası öneririz.

- **Güvenli**

   **/ CLR: safe kullanım dışı**. Seçeneği, Visual Studio 2017'de kaldırılır. Güvenli MSIL C# için gereken kod bağlantı noktası öneririz.

- **noAssembly**

   **kullanım dışı /CLR:noAssembly**. Kullanım [/LN (MSIL modülü Oluştur)](ln-create-msil-module.md) yerine.

   Bir derleme bildirimi çıkış dosyası içine eklenmesi gerektiğini değil belirtir. Varsayılan olarak, **noAssembly** seçeneği geçerli değil.

   Derleme meta verileri bildiriminde yok yönetilen bir program olarak bilinen bir *Modülü*. **NoAssembly** seçeneği, yalnızca bir modül üretmek için kullanılabilir. Kullanarak derleme yaparsanız [/c](c-compile-without-linking.md) ve **/clr:noAssembly**, ardından belirtin [noassembly](noassembly-create-a-msil-module.md) bir modül oluşturma seçeneği bağlayıcıya aşamasındadır.

   Visual C++ 2005 önce **/clr:noAssembly** gerekli **/LD**. **/LD** belirttiğinizde artık örtük **/clr:noAssembly**.

- **initialAppDomain**

   CLR sürüm 1 çalıştırmak Visual C++ uygulaması sağlar.  Kullanılarak derlenmiş bir uygulama **initialAppDomain** CLR 1. sürümü desteklenmediği için ASP.NET kullanan bir uygulama tarafından kullanılmamalıdır.

- **nostdlib**

   Derleyicinin varsayılan \clr dizin yok saymasını yönlendirir. Bir DLL System.dll gibi birden çok sürümünü ekliyorsanız derleyici hataları oluşturur. Bu seçeneği kullanarak derleme sırasında kullanılacak belirli framework belirtmenize olanak sağlar.

## <a name="remarks"></a>Açıklamalar

Yönetilen kod inceledi ve CLR tarafından yönetilen koddur. Yönetilen kod, yönetilen nesnelere erişebilir. Daha fazla bilgi için [/CLR kısıtlamalar](clr-restrictions.md).

Tanımlama ve yönetilen türleri kullanma uygulamaları geliştirme hakkında daha fazla bilgi için bkz: [çalışma zamanı platformları için bileşen uzantıları](../../windows/component-extensions-for-runtime-platforms.md).

Kullanılarak derlenmiş bir uygulama **/CLR** olabilir veya yönetilen veri içermeyebilir.

Yönetilen bir uygulama üzerinde hata ayıklamayı etkinleştirmek için bkz: [assemblydebug (DebuggableAttribute ekleme)](assemblydebug-add-debuggableattribute.md).

Yalnızca CLR Türleri atık toplanan yığında örneği oluşturulur. Daha fazla bilgi için [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md). Bir işlev yerel kod olarak derlemek için kullanın `unmanaged` pragması. Daha fazla bilgi için [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).

Varsayılan olarak, **/CLR** etkili değildir. Zaman **/CLR** kıyaslandığında geçerli **/MD** ayrıca etkilidir. Daha fazla bilgi için [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](md-mt-ld-use-run-time-library.md). **/ MD** dinamik olarak bağlanmış, çok iş parçacıklı çalışma zamanı yordamları sürümleri standart üstbilgi (.h) dosyalarından seçilmesini sağlar. CLR çöp toplayıcısı sonlandırıcılar yardımcı bir iş parçacığında çalıştığı için programlama yönetilen için çoklu iş parçacığı kullanımı gereklidir.

Kullanarak derleme yaparsanız **/c**, CLR türü ile elde edilen çıkış dosyasının belirttiğiniz [/CLRIMAGETYPE](clrimagetype-specify-type-of-clr-image.md).

**/ CLR** gelir **/eha**ve başka hiçbir **/EH** seçenekleri için desteklenen **/CLR**. Daha fazla bilgi için [/EH (özel durum işleme modeli)](eh-exception-handling-model.md).

Bir dosyanın CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](clrheader.md).

Bağlayıcının belirli bir çağrıya geçirilen tüm modüller, aynı çalışma zamanı kitaplığı derleyici seçeneğini kullanarak derlenmelidir (**/MD** veya **/LD**).

Kullanım [koduna konmaz](assemblyresource-embed-a-managed-resource.md) kaynak derlemede katıştırmak üzere bağlayıcı seçeneği. [/ DELAYSIGN](delaysign-partially-sign-an-assembly.md), [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md), ve [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bağlayıcı seçenekleri de izin, bir derlemenin nasıl oluşturulacağını özelleştirin.

Zaman **/CLR** kullanılan `_MANAGED` sembol 1 olacak şekilde tanımlandı. Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

Genel değişkenler bir yerel nesne dosyasında başlatılır (sırasında yürütülebilir dosya DLL ise DllMain) ve ardından genel değişkenleri yönetilen bölümünde (yönetilen kod çalıştırmadan önce) başlatılır. `#pragma` [init_seg](../../preprocessor/init-seg.md) yalnızca yönetilen ve yönetilmeyen kategorilerde başlatma sırası etkiler.

## <a name="metadata-and-unnamed-classes"></a>Meta veri ve adlandırılmamış sınıfları

Adsız sınıf, meta verilerinde aşağıdaki gibi görünür: `$UnnamedClass$` *crc-ın-geçerli-dosya adı*`$`*dizin*`$`burada *dizin*sıralı derleme adlandırılmamış sınıflarda sayısıdır. Örneğin, aşağıdaki kod örneği, meta verilerde adlandırılmamış bir sınıf oluşturur.

```cpp
// clr_unnamed_class.cpp
// compile by using: /clr /LD
class {} x;
```

İldasm.exe meta verileri görüntülemek için kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
