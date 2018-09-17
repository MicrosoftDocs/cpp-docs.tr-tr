---
title: -Os, -Ot (küçük koda, hızlı koda ayrıcalık) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs:
- C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a6e2f6c8b18f2af6a78857225e153cf57365fa9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699841"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (Küçük Koda Ayrıcalık Tanı, Hızlı Koda Ayrıcalık Tanı)

Simge durumuna küçültür veya ve exe ve dll boyutunu en üst düzeye çıkarır.

## <a name="syntax"></a>Sözdizimi

```
/Os
/Ot
```

## <a name="remarks"></a>Açıklamalar

**/OS** (küçük koda ayrıcalık tanı) derleyicinin boyut hız yerine boyuta ayrıcalık tanımasını sağlar ve exe ve dll boyutunu azaltır. Derleyici, makine kodu işlevsel olarak benzer dizileri için birçok C ve C++ yapıları azaltabilir. Bazen bu farklılıkları avantajsız yönleri hızı karşı boyutu sunar. **/Os** ve **/Ot** seçeneklerden biri diğerine bir tercihini belirtmenize olanak tanır:

**/Ot** (hızlı koda ayrıcalık tanı) derleyicinin boyutu hızlı yönlendirerek ve exe ve dll hızına büyütür. (Varsayılan değer budur.) Derleyici, makine kodu işlevsel olarak benzer dizileri için birçok C ve C++ yapıları azaltabilir. Bazen bu farklılıkları avantajsız yönleri hızı karşı boyutu sunar. /Ot seçeneği en üst düzeye hızını kapsanıyor ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) seçeneği. **/O2** seçeneği çok hızlı kod üretmek için çeşitli seçenekler birleştirir.

Kullanırsanız **/Os** veya **/Ot**, sonra da belirtmeniz gerekir [/Og](../../build/reference/og-global-optimizations.md) kodu en iyi duruma getirme.

> [!NOTE]
>  Test çalıştırmalarını profil oluşturmadan toplanan bilgileri geçersiz kılma belirtirseniz, aksi takdirde etkili olacak en iyi duruma getirme **/Ob**, **/Os**, veya **/Ot**. Daha fazla bilgi için [permutasyonları iyileştirmeleri](../../build/reference/profile-guided-optimizations.md).

**x86 belirli**

Aşağıdaki kod örneği, küçük koda arasındaki farkı gösterir (**/Os**) seçenekleri ve ayrıcalık hızlı koda ayrıcalık tanı (**/Ot**) seçeneği:

> [!NOTE]
>  Kullanırken aşağıdaki beklenen davranışı açıklar **/Os** veya **/Ot**. Ancak, derleyici davranışı yapma farklı iyileştirmeler için aşağıdaki kodu neden olabilir.

```
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

Aşağıdaki makine kod parçasını gösterildiği, zaman DIFFER.c derlendiği boyutu (**/Os**), derleyici uygular dönüş deyimindeki ifade Çarp açık olarak bir Çarp kod kısa ancak daha yavaş bir dizi oluşturmak için:

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Alternatif olarak, ne zaman DIFFER.c derlendiği hızını (**/Ot**), derleyici uygular üst karakter dizisi olarak dönüş deyimindeki ifade çarpın ve `LEA` kod hızlı ancak uzun bir dizi oluşturmak için yönergeler:

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**Son x86 belirli**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **iyileştirme** özellik sayfası.

1. Değiştirme **boyut veya hız ayrıcalığı** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)