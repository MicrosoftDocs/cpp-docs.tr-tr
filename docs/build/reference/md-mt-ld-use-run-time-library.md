---
description: Daha fazla bilgi edinin:/MD,/MT,/LD (Run-Time kitaplığı kullanın)
title: /MD,-MT,-LD (Run-Time kitaplığı kullanın)
ms.date: 07/17/2019
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
ms.openlocfilehash: db7d5be50145cc5dc422e7d7c417f519d8f07076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137871"
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)

Çok iş parçacıklı bir modülün bir DLL olup olmadığını belirtir ve çalışma zamanı kitaplığının perakende veya hata ayıklama sürümlerini gösterir.

## <a name="syntax"></a>Syntax

```
/MD[d]
/MT[d]
/LD[d]
```

## <a name="remarks"></a>Açıklamalar

|Seçenek|Açıklama|
|------------|-----------------|
|**/MD**|Uygulamanın, çalışma zamanı kitaplığının çok iş parçacığına özgü ve DLL'ye özgü sürümlerini kullanmasını sağlar. `_MT`Ve `_DLL` DERLEYICISININ, Msvcrt. lib kitaplık adını. obj dosyasına yerleştirmesini sağlar.<br /><br /> Bu seçenekle derlenen uygulamalar, statik olarak MSVCRT.lib öğesine bağlıdır. Bu kitaplık, bağlayıcının dış başvuruları çözümlemesini sağlayan bir kod katmanı sağlar. Gerçek çalışma kodu MSVCR *versionNumber* içinde bulunur. DLL, MSVCRT. lib ile bağlantılı uygulamalara çalışma zamanında kullanılabilir olmalıdır.|
|**/MDd**|`_DEBUG`, Ve tanımlar, `_MT` uygulamanın, `_DLL` çalışma zamanı kitaplığının çok Iş parçacıklı ve DLL 'ye özgü sürümünü kullanmasını sağlar. Ayrıca, derleyicinin MSVCRTD.lib kitaplık adını .obj dosyasına yerleştirmesini sağlar.|
|**/MT**|Uygulamanın, çalışma zamanı kitaplığının çok iş parçacığı, statik sürümünü kullanmasını sağlar. `_MT`DERLEYICININ Libcmt. lib kitaplık adını. obj dosyasına yerleştirmesini, böylece bağlayıcının dış sembolleri çözümlemek IÇIN LIBCMT. lib kullanmasını sağlar.|
|**/MTd**|`_DEBUG`Ve tanımlar `_MT` . Bu seçenek, aynı zamanda, derleyicinin LIBCMTD.lib kitaplık adını .obj dosyasına koyarak bağlayıcının dış simgeleri çözme sırasında LIBCMTD.lib kullanmasını sağlar.|
|**/LD**|DLL oluşturur.<br /><br /> **/DLL** seçeneğini bağlayıcıya geçirir. Bağlayıcı, bir işlev için arar, ancak gerektirmez `DllMain` . Bir `DllMain` işlev yazarsanız, BAĞLAYıCı `DllMain` doğru döndüren bir işlev ekler.<br /><br /> DLL başlatma kodunu bağlar.<br /><br /> Komut satırında dışa aktarma (.exp) dosyası belirtilmezse, içeri aktarma kitaplığı (.lib) oluşturur. İçeri aktarma kitaplığını DLL'nizi çağıran uygulamalara bağlarsınız.<br /><br /> [/Fe 'yi (ad exe dosyası)](fe-name-exe-file.md) bir. exe dosyası yerıne bir dll olarak adlandırmayla yorumlar. Varsayılan olarak, program adı *baseName*. exe yerine *baseName*. dll olur.<br /><br /> Açıkça **/md** belirtmediğiniz takdirde **/MT** 'i belirtir.|
|**/LDd**|Hata ayıklama DLL'si oluşturur. `_MT`Ve tanımlar `_DEBUG` .|

C çalışma zamanı kitaplıkları ve [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)ile derleme yaparken hangi kitaplıkların kullanıldığı hakkında daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

Belirli bir bağlayıcı çağrısına geçirilen tüm modüller aynı çalışma zamanı kitaplığı derleyici seçeneğiyle derlenmiş olmalıdır (**/md**, **/MT**, **/ld**).

Çalışma zamanı kitaplıklarının hata ayıklama sürümlerini kullanma hakkında daha fazla bilgi için bkz. [C Run-Time kitaplığı başvurusu](../../c-runtime-library/c-run-time-library-reference.md).

Dll 'Ler hakkında daha fazla bilgi için bkz. [Visual Studio 'Da C/C++ dll 'Leri oluşturma](../dlls-in-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **kod oluşturma** özellik sayfasını seçin.

1. **Çalışma zamanı kitaplığı** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
