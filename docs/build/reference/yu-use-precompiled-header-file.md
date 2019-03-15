---
title: /Yu (Önceden Derlenmiş Başlık Dosyasını Kullanma)
ms.date: 11/04/2016
f1_keywords:
- /yu
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
ms.openlocfilehash: c0dcb045450d6e6eca31b8c76a92726e62400656
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810126"
---
# <a name="yu-use-precompiled-header-file"></a>/Yu (Önceden Derlenmiş Başlık Dosyasını Kullanma)

Derleyicinin geçerli derlemede varolan önceden derlenmiş üst bilgi (.pch) dosyasını kullanmak için sağlar.

## <a name="syntax"></a>Sözdizimi

```
/Yu[filename]
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Kullanılarak kaynak dosyasında yer alan bir üst bilgi dosyasının adını bir **#include** önişlemci yönergesi.

## <a name="remarks"></a>Açıklamalar

İçerme dosyasının adını hem de aynı olmalıdır **/Yc** seçeneği önceden derlenmiş üst bilgi ve tüm oluşturan sonraki **/Yu** seçeneği önceden derlenmiş üst bilgi kullanımını gösteren.

İçin **/Yc**, `filename` noktada belirtir hangi ön derleme durur; yine de tüm kod derleyici işlemini gerçekleştirir `filename` ve temel bir içerme dosyası ve bir uzantı adını kullanarak elde edilen önceden derlenmiş üst bilgi adları .PCH.

.Pch dosyası kullanılarak oluşturulmuş olması gerekir **/Yc**.

Derleyici .h dosyası olarak derlenmiş önce gerçekleşen tüm kodu değerlendirir. Bunu yalnızca ötesine atlar **#include** .h dosyası ile ilişkili yönergesi .pch dosyasında yer alan kod kullanır ve ardından sonra tüm kodu derler `filename`.

Komut satırında arasında boşluk izin **/Yu** ve `filename`.

Belirttiğinizde **/Yu** seçeneği olmadan bir dosya adı, kaynak programınızı içermelidir bir [#pragma hdrstop](../../preprocessor/hdrstop.md) .pch dosyası Adlandır önceden derlenmiş üst bilgi dosyası adını belirten pragması. Bu durumda, derleyici tarafından adlandırılan önceden derlenmiş üst bilgi (.pch dosyası Adlandır) kullanacağı [FP (adı. PCH dosyası)](fp-name-dot-pch-file.md). Derleyici, bu pragma konumuna atlar, derlenmiş halin pragması tarafından belirlenen önceden derlenmiş üstbilgi dosyasından geri yükler ve ardından pragmayı izleyen kodu derler. Varsa **#pragma hdrstop** derleyici görünüyor .pch uzantılı kaynak dosyanın temel adı türetilen bir ada sahip bir dosya için bir dosya adı belirtmiyor. Ayrıca **/FP** farklı .pch dosyası belirtmek için seçeneği.

Belirtirseniz **/Yu** seçeneği olmadan bir dosya adı ve belirtmek başarısız bir **hdrstop** pragması, bir hata iletisi oluşturulur ve derleme başarısız olur.

Varsa **/Yc** `filename` ve **/Yu** `filename` seçeneklerini aynı komut satırında oluşur ve her ikisi de aynı dosya adına başvuru **/Yc** `filename` alır öncelik kadar tüm kodu önceden derlemek ve adlandırılmış dosyası dahil. Bu özellik, derleme görevleri dosyalarını yazımını basitleştirir.

.PCH dosyaları makine ortamı hakkında bilgi bilgilerinin yanı sıra bellek adresi program içerdiğinden, yalnızca oluşturulduğu, makinedeki bir pch dosyası kullanmanız gerekir.

Önceden derlenmiş üst bilgiler hakkında daha fazla bilgi için bkz:

- [/Y (Önceden Derlenmiş Üst Bilgiler)](y-precompiled-headers.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Belirtin [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](yc-create-precompiled-header-file.md) projenizdeki bir .cpp dosyası üzerinde.

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önceden derlenmiş üst bilgiler** özellik sayfası.

1. Değiştirme **dosya üzerinden PCH Oluştur/Kullan** özelliği veya **önceden derlenmiş üst bilgi Oluştur/Kullan** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.

## <a name="examples"></a>Örnekler

Aşağıdaki kodu:

```
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
...
```

komut satırı ile derlenmiş `CL /YuMYAPP.H PROG.CPP`, derleyici üç işlemez deyimleri ancak MYAPP.pch, kullanan önceden derlenmiş koddan böylece dosyaları (ve bunlar içerebilir herhangi bir dosya) üç önişlemde harcanan süreyi kaydetmeyi içerir.

Kullanabileceğiniz [FP (adı. PCH dosyası)](fp-name-dot-pch-file.md) seçeneğini **/Yu** adı ya da dosya adı bağımsız değişkeni için farklı ise .pch dosyası adını belirtmek için seçeneği **/Yc** veya giriş olarak kaynak dosyanın temel adı Aşağıdaki:

```
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP
```

Bu komut MYPCH.pch adlı bir ön derlenmiş üstbilgi dosyası belirtir. Derleyici içeriğinin tüm üst bilgi dosyaları'kurmak için ve de dahil olmak üzere MYAPP.h önceden derlenmiş durumunu geri yüklemek için kullanır. Derleyici, ardından MYAPP.h sonra oluşan kodu derler **dahil** deyimi.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
