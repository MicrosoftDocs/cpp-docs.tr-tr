---
title: /MD,-MT,-LD (çalışma zamanı kitaplığını kullan)
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
ms.openlocfilehash: 4e734233d94bf57d6838bd4d37c023d55f1d5f6b
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299759"
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)

Çok iş parçacıklı bir modülün bir DLL olup olmadığını belirtir ve çalışma zamanı kitaplığının perakende veya hata ayıklama sürümlerini gösterir.

## <a name="syntax"></a>Sözdizimi

```
/MD[d]
/MT[d]
/LD[d]
```

## <a name="remarks"></a>Açıklamalar

|Seçenek|Açıklama|
|------------|-----------------|
|**/MD**|Uygulamanın, çalışma zamanı kitaplığının çok iş parçacığına özgü ve DLL'ye özgü sürümlerini kullanmasını sağlar. `_MT` Ve`_DLL` derleyicisinin, Msvcrt. lib kitaplık adını. obj dosyasına yerleştirmesini sağlar.<br /><br /> Bu seçenekle derlenen uygulamalar, statik olarak MSVCRT.lib öğesine bağlıdır. Bu kitaplık, bağlayıcının dış başvuruları çözümlemesini sağlayan bir kod katmanı sağlar. Gerçek çalışma kodu MSVCR*versionNumber*içinde bulunur. DLL, MSVCRT. lib ile bağlantılı uygulamalara çalışma zamanında kullanılabilir olmalıdır.|
|**/MDd**|, `_DEBUG` Vetanımlar`_DLL` , uygulamanın, çalışma zamanı kitaplığının çok iş parçacıklı ve DLL 'ye özgü sürümünü kullanmasını sağlar. `_MT` Ayrıca, derleyicinin MSVCRTD.lib kitaplık adını .obj dosyasına yerleştirmesini sağlar.|
|**/MT**|Uygulamanın, çalışma zamanı kitaplığının çok iş parçacığı, statik sürümünü kullanmasını sağlar. `_MT` Derleyicinin Libcmt. lib kitaplık adını. obj dosyasına yerleştirmesini, böylece bağlayıcının dış sembolleri çözümlemek için Libcmt. lib kullanmasını sağlar.|
|**/MTd**|`_DEBUG` Ve`_MT`tanımlar. Bu seçenek, aynı zamanda, derleyicinin LIBCMTD.lib kitaplık adını .obj dosyasına koyarak bağlayıcının dış simgeleri çözme sırasında LIBCMTD.lib kullanmasını sağlar.|
|**/LD**|DLL oluşturur.<br /><br /> **/DLL** seçeneğini bağlayıcıya geçirir. Bağlayıcı, bir `DllMain` işlev için arar, ancak gerektirmez. Bir `DllMain` işlev yazarsanız, bağlayıcı doğru döndüren bir `DllMain` işlev ekler.<br /><br /> DLL başlatma kodunu bağlar.<br /><br /> Komut satırında dışa aktarma (.exp) dosyası belirtilmezse, içeri aktarma kitaplığı (.lib) oluşturur. İçeri aktarma kitaplığını DLL'nizi çağıran uygulamalara bağlarsınız.<br /><br /> [/Fe 'yi (ad exe dosyası)](fe-name-exe-file.md) bir. exe dosyası yerıne bir dll olarak adlandırmayla yorumlar. Varsayılan olarak, program adı *baseName*. exe yerine *baseName*. dll olur.<br /><br /> Açıkça **/md**belirtmediğiniz takdirde **/MT** 'i belirtir.|
|**/LDd**|Hata ayıklama DLL'si oluşturur. `_MT` Ve`_DEBUG`tanımlar.|

C çalışma zamanı kitaplıkları ve [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)ile derleme yaparken hangi kitaplıkların kullanıldığı hakkında daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

Belirli bir bağlayıcı çağrısına geçirilen tüm modüller aynı çalışma zamanı kitaplığı derleyici seçeneğiyle derlenmiş olmalıdır ( **/md**, **/MT**, **/ld**).

Çalışma zamanı kitaplıklarının hata ayıklama sürümlerini kullanma hakkında daha fazla bilgi için bkz. [C çalışma zamanı kitaplığı başvurusu](../../c-runtime-library/c-run-time-library-reference.md).

Dll 'Ler hakkında daha fazla bilgi için bkz. [Visual Studio 'Da CC++ /dll oluşturma](../dlls-in-visual-cpp.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++/** komut > **satırı** Özellik sayfası ' nı seçin.

1. **Kod oluşturma** özellik sayfasını seçin.

1. **Çalışma zamanı kitaplığı** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
