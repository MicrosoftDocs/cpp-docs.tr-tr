---
title: /Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)
ms.date: 1/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: e435b48359a708408ff8659e53c9e7c4f7e80261
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619121"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)

**/Tc** seçeneği belirtir, dosya adı bağımsız değişkeni bir C kaynak dosyası olduğunu bile .c uzantısı yok. **/Tp** seçeneği belirtir, dosya adı bağımsız değişkeni bir C++ kaynak dosyası olduğunu .cpp veya .cxx uzantısını almasa bile. Seçeneğini ve dosya adı arasında boşluk isteğe bağlıdır. Her seçenek bir dosya belirtir; Ek dosyaları belirtmek için seçeneği yineleyin.

**/TC** ve **/TP** genel çeşitleri olan **/Tc** ve **/Tp**. Derleyicinin komut satırında C kaynak dosyalarında adlı tüm dosyaları belirtin (**/TC**) veya C++ kaynak dosyaları (**/TP**), komut satırı seçeneği ile ilgili olarak konumuna bakılmaksızın. Bu genel seçenekler yoluyla tek bir dosya çubuğunda geçersiz kılınabilir **/Tc** veya **/Tp**.

## <a name="syntax"></a>Sözdizimi

> **/TC** _filename_
>  **/Tp** _filename_
>  **/TC** 
>  **/TP**

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Bir C veya C++ kaynak dosyası.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **CL** .c uzantılı dosyaları C kaynak dosyalarında olduğu ve dosyalar .cpp veya .cxx uzantısını ile C++ kaynak dosyaları varsayar.

Zaman ya da **TC** veya **Tc** seçeneği belirtildiğinde, tüm belirtimi [/ZC: wchar_t (wchar_t yerel türü olduğu)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) seçeneği yoksayılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Gelişmiş** özellik sayfası.

1. Değiştirme **derleme olarak** özelliği. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri uygulamak için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Örnekler

Bu CL komut satırı MAIN.c TEST.prg ve COLLATE.prg C kaynak dosyalarının tümünü olduğunu belirtir. CL PRINT.prg tanımaz.

> CL ANA. C /TcTEST.PRG /TcCOLLATE.PRG yazdır. PRG

C++ dosyaları olarak TEST1.c, TEST2.cxx TEST3.huh ve TEST4.o derlenir ve TEST5.z C dosyası olarak derlenmiş olan bu CL komut satırı belirtir.

> CL TEST1. C TEST2. CXX TEST3. HUH TEST4. /Tc TEST5 O. Z /TP

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
